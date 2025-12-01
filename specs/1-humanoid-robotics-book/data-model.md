# Data Model: Humanoid Robotics Book Content Guidelines

**Feature Branch**: `1-humanoid-robotics-book`
**Date**: 2025-11-30
**Spec**: [specs/1-humanoid-robotics-book/spec.md](specs/1-humanoid-robotics-book/spec.md)

## Entities

### Chapter
- Represents a primary organizational unit of the book.
- **Attributes**:
    - `id`: Unique identifier (string)
    - `title`: Chapter title (string)
    - `purpose`: Description of the chapter's purpose (string)
    - `learning_outcomes`: List of key learning objectives (list of strings)
    - `key_concepts`: List of core concepts introduced (list of strings)
    - `content`: Markdown content of the chapter (string)
    - `sidebar_position`: Docusaurus sidebar position (integer)
    - `metadata`: Structured data for RAG/Qdrant (object, see Metadata entity)
- **Relationships**:
    - Contains multiple `Sub-chapter` entities.
    - Contains multiple `Section` entities.

### Sub-chapter
- Represents a secondary organizational unit within a chapter.
- **Attributes**:
    - `id`: Unique identifier (string)
    - `title`: Sub-chapter title (string)
    - `content`: Markdown content of the sub-chapter (string)
    - `parent_chapter_id`: Reference to parent Chapter (string)
    - `metadata`: Structured data for RAG/Qdrant (object)
- **Relationships**:
    - Belongs to one `Chapter` entity.
    - Contains multiple `Section` entities.

### Section
- Represents a detailed part within a sub-chapter or directly under a chapter.
- **Attributes**:
    - `id`: Unique identifier (string)
    - `title`: Section title (string)
    - `content`: Markdown content of the section (string)
    - `parent_id`: Reference to parent Chapter or Sub-chapter (string)
    - `metadata`: Structured data for RAG/Qdrant (object)
- **Relationships**:
    - Belongs to one `Chapter` or `Sub-chapter` entity.

### Diagram/Figure
- Represents a visual representation within the book.
- **Attributes**:
    - `id`: Unique identifier (string)
    - `alt_text`: Textual description for accessibility and RAG (string)
    - `file_path`: Path to image file (e.g., `/static/img/diagram.png`) (string)
    - `caption`: Description displayed with the image (string)
    - `associated_section_id`: Reference to the section where it appears (string)

### Code Example
- Represents a block of code demonstrating robotics or AI concepts.
- **Attributes**:
    - `id`: Unique identifier (string)
    - `language`: Programming language (e.g., Python, C++) (string)
    - `code_snippet`: The actual code block (string)
    - `description`: Explanation of the code's purpose (string)
    - `associated_section_id`: Reference to the section where it appears (string)

### Glossary Term
- Represents a key technical term with its definition.
- **Attributes**:
    - `term`: The technical term (string)
    - `definition`: Clear, concise explanation (string)
    - `chapter_references`: List of chapters where the term is used (list of strings)

### Metadata
- Structured information for RAG and search optimization.
- **Attributes**:
    - `text`: The raw text chunk (string)
    - `file`: Source Markdown file path (string)
    - `chunk_id`: Unique identifier for the text chunk (string)
    - `heading`: Closest preceding Markdown heading (string)
    - `keywords`: List of relevant keywords extracted from the chunk (list of strings)
    - `embedding`: Vector representation of the text chunk (vector of floats - **DO NOT STORE, only used at ingestion/query time**)
