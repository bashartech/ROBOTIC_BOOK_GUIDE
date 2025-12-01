<!--
Sync Impact Report:
Version change: None → 1.0.0
List of modified principles: All (new constitution)
Added sections: All (new constitution)
Removed sections: None
Templates requiring updates:
- .specify/templates/plan-template.md ⚠ pending
- .specify/templates/spec-template.md ⚠ pending
- .specify/templates/tasks-template.md ⚠ pending
- .specify/templates/commands/*.md ⚠ pending
Follow-up TODOs: None
-->
# Humanoid Robotics Book Constitution

## Core Principles

### I. Consistent Book Structure
Divide the book into clear chapters and sub-chapters, each following a consistent structure. Every chapter must begin with: Purpose, Learning outcomes, and Key concepts. Chapters must include: Explanations, Tables, Diagrams (described with text), Real-world examples, and Case studies. Ensure the writing style is: Professional, Technical, Accessible for learners, and Free of unnecessary complexity. Include margin notes or info boxes (e.g., Note, Warning, Key Idea). Use consistent Markdown formatting for headings, tables, lists, and code blocks. All chapters must be written to be RAG friendly: Short paragraphs, Clear headings, Logical sections, and each sub-chapter should be self-contained so Qdrant vector search works accurately.

### II. Docusaurus and Qdrant Compatibility
The book must be fully compatible with Docusaurus documentation format. All content must be structured so it can be ingested by Qdrant Cloud, supporting RAG retrieval, embedding search, and context-based question answering. The constitution should guide chapters to be written in a format ideal for: Chunking and Clean metadata extraction (title, headings, etc.). Include instructions for maintaining: Markdown consistency and Title hierarchy (H1 → H2 → H3), avoiding extremely long paragraphs. Each chapter should be placed inside a dedicated folder. Frontmatter for each file should follow Docusaurus rules (title, sidebar_position). Suggest a sidebar structure based on the main chapters. Include recommendations for: Versioning, Search optimization, and Navigation layout. Encourage adding images/diagrams via /static/img if needed. Suggest keeping file names short, clean, and lowercase (for GitHub Pages compatibility).

### III. RAG, Qdrant, and Chatbot Technical Requirements
The book should define clear semantic boundaries between sections for vector search clarity. Each chapter must maintain explicit headings, so Qdrant metadata remains meaningful. Ensure the content is fact-based, structured, and contextual so retrieval matches user queries. Encourage placement of keywords and terminology lists per chapter to improve RAG accuracy. Suggest including a “technical appendix” for data structures, algorithms, and definitions to improve search recall. Provide suggestions for including cross-reference links within chapters for better navigation in the chatbot. Ensure the constitution encourages writing content in a way suitable for: Embedding models, Vector similarity, and Query matching. Suggest embedding-friendly formatting (shorter bullet points, tables, key phrases).

### IV. Chatbot + Embedded RAG System Compatibility
The book must be compatible with an embedded chatbot inside Docusaurus. Content should be structured so the chatbot can: Answer questions only from the book and Answer questions from selected text (contextual QA). Chapters must include: Clear definitions, Structured explanations, Summaries, and FAQs. These features improve chatbot performance. Provide guidance that every section must be written to support: Query → embedding → vector search → answer workflow. Suggest adding a “Chatbot Interaction Guide” in the book (optional).

### V. Professional Quality Standards
All concepts must be accurate, technically correct, and sourced from robotics/AI best practices. No vague statements — every claim must be logically supported. No duplicated content across chapters. No excessively lengthy paragraphs; maintain readable pacing. Use real-world robotics examples (Tesla Optimus, Atlas, Unitree, etc.) where relevant. Provide ethical considerations and safety guidelines. Ensure terminology is consistent throughout the book. Encourage the agent to write with: Engineering clarity, Academic tone, and Step-by-step explanations where needed. Include recommended further reading or external resources (optional). Add exercises or review questions to strengthen understanding.

### VI. Professional Book Outline Guidelines
Start with an introduction chapter explaining the purpose of the book. Divide topics into logical sections: Fundamentals, Advanced concepts, Case studies, Future trends, and Appendices. Ensure all chapters include: Explanation, Diagrams (described textually), Tables, and Examples. Maintain a progressive flow: Beginner → intermediate → advanced. Include real engineering workflows for humanoid robotics wherever relevant. Encourage inclusion of practical sections: System design, Coding examples, and Robotics simulations. Add a glossary at the end for key terms.

### VII. Special Hackathon Constraints
The book must support two projects: Book writing and RAG-based chatbot. Content should be easily ingestible by a Gemini embeddings model (since you are using Gemini instead of OpenAI). Constitution must ensure the book is always: Searchable, Indexable, and Structured for vector retrieval. Ensure content guidelines match: Qdrant Cloud free tier limitations and Efficient chunking requirements. Constitution should support spec-driven development, meaning no missing components.

## Technical Specification Requirements

This section summarizes the technical details required by the constitution for all content, including: Docusaurus frontmatter, Markdown consistency, Title hierarchy (H1->H2->H3), clear semantic boundaries for vector search, explicit headings, content structure for embedding models, and efficient chunking requirements.

## Development and Quality Workflow

This section covers the quality rules and guidelines, including: accuracy, no vague statements, no duplicated content, readability, use of real-world examples, ethical considerations, consistent terminology, engineering clarity, academic tone, and step-by-step explanations. It also includes the integration with the chatbot and RAG system, ensuring content is QA-ready.

## Governance
Constitution supersedes all other practices. Amendments require documentation, approval, and a migration plan. All content created must verify compliance with these principles. Complexity must be justified. This constitution supports spec-driven development, ensuring no missing components.

**Version**: 1.0.0 | **Ratified**: 2025-11-30 | **Last Amended**: 2025-11-30
