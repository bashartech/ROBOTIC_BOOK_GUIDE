# Quickstart Guide: Humanoid Robotics Book with RAG Chatbot

This guide provides a quick overview of how to set up and run the Humanoid Robotics Book project, including content generation, RAG ingestion, FastAPI backend, and Docusaurus frontend.

## 1. Project Structure

The project is divided into two main parts:

- `backend/`: Contains the FastAPI application responsible for the RAG chatbot logic, Qdrant integration, and Gemini embeddings.
- `frontend/`: Hosts the Docusaurus documentation website, which displays the generated book content.

## 2. Setup

### Prerequisites

- Python 3.12+
- Node.js (for Docusaurus)
- Git
- Qdrant Cloud account (Free Tier is sufficient)
- Gemini API Key

### Backend Setup

1.  **Clone the repository**:

    ```bash
    git clone <repository_url>
    cd <repository_name>
    ```

2.  **Navigate to the backend directory**:

    ```bash
    cd backend
    ```

3.  **Create a virtual environment and install dependencies**:

    ```bash
    python -m venv venv
    .\venv\Scripts\activate  # On Windows PowerShell
    # source venv/bin/activate  # On Linux/macOS
    pip install -r requirements.txt
    ```

4.  **Configure environment variables**:

    Create a `.env` file in the `backend/` directory with your Qdrant and Gemini credentials:

    ```
    QDRANT_HOST=your_qdrant_host
    QDRANT_API_KEY=your_qdrant_api_key
    GEMINI_API_KEY=your_gemini_api_key
    ```

5.  **Run the FastAPI application**:

    ```bash
    uvicorn main:app --reload
    ```

    The API will be accessible at `http://127.0.0.1:8000`.

### Frontend Setup (Docusaurus)

1.  **Navigate to the frontend directory**:

    ```bash
    cd frontend
    ```

2.  **Install dependencies**:

    ```bash
    npm install
    ```

3.  **Start the Docusaurus development server**:

    ```bash
    npm start
    ```

    The book will be accessible at `http://localhost:3000`.

## 3. Book Content Generation

To generate the book chapters, you will use the Claude Code agent to write Markdown files into the `frontend/docs` directory, following the guidelines in `specs/1-humanoid-robotics-book/spec.md` and `specs/1-humanoid-robotics-book/plan.md`.

## 4. RAG Ingestion

Once the Markdown book content is available in `frontend/docs`, you can trigger the ingestion process via the FastAPI backend:

```bash
curl -X POST "http://127.0.0.1:8000/ingest" -H "Content-Type: application/json" -d '{}'
```

This will chunk the text, embed it using Gemini, and upload it to your Qdrant Cloud collection.

## 5. Chatbot Interaction

You can interact with the RAG chatbot via the FastAPI endpoints:

- **General Question**:

    ```bash
    curl -X POST "http://127.0.0.1:8000/ask" -H "Content-Type: application/json" -d '{"query": "What is inverse kinematics?"}'
    ```

- **Context-based Question**:

    ```bash
    curl -X POST "http://127.0.0.1:8000/context-question" -H "Content-Type: application/json" -d '{"query": "What are the benefits of this approach?", "context": "A modular robotics design allows for easy component replacement and upgrades."}'
    ```

