---
id: 1
title: create humanoid robotics book constitution
stage: constitution
date: 2025-11-30
surface: agent
model: claude-sonnet-4-5-20250929
feature: none
branch: main
user: user
command: /sp.constitution
labels: ["constitution", "book-guidelines", "hackathon"]
links:
  spec: null
  ticket: null
  adr: null
  pr: null
files:
  - .specify/memory/constitution.md
tests: []
---

## Prompt

'''
# A. General Book Structure Guidelines

These points help the agent create a well-organized, professional book:

Divide the book into clear chapters and sub-chapters, each following a consistent structure.

Every chapter must begin with:

Purpose

Learning outcomes

Key concepts

Chapters must include:

Explanations

Tables

Diagrams (described with text since the book is Markdown)

Real-world examples

Case studies

Ensure the writing style is:

Professional

Technical

Accessible for learners

Free of unnecessary complexity

Include margin notes or info boxes (e.g., Note, Warning, Key Idea).

Use consistent Markdown formatting for headings, tables, lists, and code blocks.

All chapters should be written to be RAG friendly:

Short paragraphs

Clear headings

Logical sections

Each sub-chapter should be self-contained so Qdrant vector search works accurately.

# B. Hackathon Features That MUST Be Represented in the Book Constitution

These points ensure the agent does not miss any hackathon requirements:

The book must be fully compatible with Docusaurus documentation format.

All content must be structured so it can be ingested by Qdrant Cloud.

The book must support:

RAG retrieval

Embedding search

Context-based question answering

The constitution should guide chapters to be written in a format ideal for:

Chunking

Clean metadata extraction (title, headings, etc.)

Include instructions for maintaining:

Markdown consistency

# Title hierarchy (H1 → H2 → H3)

Avoiding extremely long paragraphs

Ensure every chapter suppons

These guidelines help Claude Code build a Docusaurus-friendly book:

Each chapter should be placed inside a dedicated folder.

Frontmatter for each file should follow Docusaurus rules (title, sidebar_position).

Suggest a sidorts chatbot answerability (QA-ready text).

C. Technical Requirements for RAG, Qdrant, and Chatbot

These suggestions must be reflected in the constitution structure:

The book should define clear semantic boundaries between sections for vector search clarity.

Each chapter must maintain explicit headings, so Qdrant metadata remains meaningful.

Ensure the content is fact-based, structured, and contextual so retrieval matches user queries.

Encourage placement of keywords and terminology lists per chapter to improve RAG accuracy.

Suggest including a “technical appendix” for data structures, algorithms, and definitions to improve search recall.

Provide suggestions for including cross-reference links within chapters for better navigation in the chatbot.

Ensure the constitution encourages writing content in a way suitable for:

Embedding models

Vector similarity

Query matching

Suggest embedding-friendly formatting (shorter bullet points, tables, key phrases).

D. Docusaurus-Specific Structure Suggestiebar structure based on the main chapters.

Include recommendations for:

Versioning

Search optimization

Navigation layout

Encourage adding images/diagrams via /static/img if needed.

Suggest keeping file names short, clean, and lowercase (for GitHub Pages compatibility).

E. Chatbot + Embedded RAG System Requirements

Include these suggestions so the agent never misses hackathon-critical features:

The book must be compatible with an embedded chatbot inside Docusaurus.

Content should be structured so the chatbot can:

Answer questions only from the book

Answer questions from selected text (contextual QA)

Chapters must include:

Clear definitions

Structured explanations

Summaries

FAQs
→ These features improve chatbot performance.

Provide guidance that every section must be written to support:

Query → embedding → vector search → answer workflow

Suggest adding a “Chatbot Interaction Guide” in the book (optional).

F. Quality Rules & Regulations for Professional Book Creation

These points ensure Claude Code maintains professional writing standards:

All concepts must be accurate, technically correct, and sourced from robotics/AI best practices.

No vague statements — every claim must be logically supported.

No duplicated content across chapters.

No excessively lengthy paragraphs; maintain readable pacing.

Use real-world robotics examples (Tesla Optimus, Atlas, Unitree, etc.) where relevant.

Provide ethical considerations and safety guidelines.

Ensure terminology is consistent throughout the book.

Encourage the agent to write with:

Engineering clarity

Academic tone

Step-by-step explanations where needed

Include recommended further reading or external resources (optional).

Add exercises or review questions to strengthen understanding.

G. Professional Book Outline Guidelines

Tell Claude Code to build the constitution using these instructions:

Start with an introduction chapter explaining the purpose of the book.

Divide topics into logical sections:

Fundamentals

Advanced concepts

Case studies

Future trends

Appendices

Ensure all chapters include:

Explanation

Diagrams (described textually)

Tables

Examples

Maintain a progressive flow:

Beginner → intermediate → advanced

Include real engineering workflows for humanoid robotics wherever relevant.

Encourage inclusion of practical sections:

System design

Coding examples

Robotics simulations

Add a glossary at the end for key terms.

H. Special Hackathon Constraints

These points must be reflected in the constitution:

The book must support two projects:

Book writing

RAG-based chatbot

Content should be easily ingestible by a Gemini embeddings model (since you are using Gemini instead of OpenAI).

Constitution must ensure the book is always:

Searchable

Indexable

Structured for vector retrieval

Ensure content guidelines match:

Qdrant Cloud free tier limitations

Efficient chunking requirements

Constitution should support spec-driven development, meaning no missing components.
'''

## Response snapshot

The project constitution for the Humanoid Robotics Book has been updated to version 1.0.0. The constitution now includes detailed guidelines covering book structure, Docusaurus and Qdrant compatibility, RAG and chatbot technical requirements, professional quality standards, book outline, and special hackathon constraints. Several template files (.specify/templates/plan-template.md, .specify/templates/spec-template.md, .specify/templates/tasks-template.md, and .specify/templates/commands/*.md) require manual review and update to align with the new constitution.

## Outcome

- ✅ Impact: The project constitution has been successfully created and updated based on the provided detailed guidelines.
- 🧪 Tests: No explicit tests were run for this task.
- 📁 Files: .specify/memory/constitution.md was modified.
- 🔁 Next prompts: None
- 🧠 Reflection: The constitution was updated successfully. The next step would be to review and update the dependent template files.

## Evaluation notes (flywheel)

- Failure modes observed: The bash script for PHR creation failed, requiring a manual fallback.
- Graders run and results (PASS/FAIL): N/A
- Prompt variant (if applicable): N/A
- Next experiment (smallest change to try): Investigate why the `create-phr.sh` script was not found.