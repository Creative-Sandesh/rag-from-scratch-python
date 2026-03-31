# Simple RAG Personal Knowledge Base Agent

A lightweight Python CLI tool that lets you chat with your personal notes. Built in under 100 lines of code, this from-scratch RAG (Retrieval-Augmented Generation) agent demonstrates semantic search and grounding using OpenAI embeddings, cosine similarity, and local JSON vector storage—no heavy frameworks required.

## Features

* **Semantic Search:** Uses OpenAI's `text-embedding-3-small` to understand the *meaning* of your questions, not just exact keyword matches.
* **Grounded Generation:** Uses `gpt-4.1-mini` with a strict prompt to ensure the AI only answers using your provided context, effectively preventing hallucinations.
* **Local Vector Database:** Stores your text chunks and their mathematical embeddings locally in a lightweight `knowledge.json` file.
* **Pure Python:** No massive frameworks like LangChain or LlamaIndex. Just pure Python, `numpy` for math, and the `openai` SDK.

## Prerequisites

* Python 3.7 or higher
* An active [OpenAI API Key](https://platform.openai.com/)

## Installation

1. **Clone or download the repository:**
   ```bash
   git clone [https://github.com/yourusername/Simple-RAG-PersonalKnowledgeBaseAgent-System.git](https://github.com/yourusername/Simple-RAG-PersonalKnowledgeBaseAgent-System.git)
   cd Simple-RAG-PersonalKnowledgeBaseAgent-System
(Optional but recommended) Create a virtual environment:

Bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
Install the required dependencies:

Bash
pip install -r requirements.txt
Set your OpenAI API Key:
Export your API key as an environment variable so the script can authenticate securely.

On macOS/Linux:

Bash
export OPENAI_API_KEY="sk-your-api-key-here"
On Windows (Command Prompt):

DOS
set OPENAI_API_KEY="sk-your-api-key-here"
Usage
Add your knowledge: Open notes.txt and paste in your personal notes. Separate distinct ideas or paragraphs with line breaks.

Run the agent:

Bash
python agent.py
Chat: The system will ingest your notes, generate embeddings, and prompt you to ask a question.

Plaintext
Ingesting notes...
Knowledge base ready.

Ask a Question: What is RAG?

sandySayzzz:
RAG systems combine retrieval with generation to produce grounded responses.

## How It Works Under the Hood
* Ingestion: Reads notes.txt line by line.

* Embedding: Converts each line into a dense mathematical vector representing its semantic meaning.

* Storage: Saves the text and vectors locally to knowledge.json.

* Retrieval: Converts your typed question into a vector and uses Cosine Similarity to find the most mathematically relevant notes in the JSON file.

* Generation: Injects the retrieved notes into a strict prompt and asks the OpenAI chat model to answer your question only using that context.

## Project Structure
Simple-RAG-PersonalKnowledgeBaseAgent-System/
│
├── agent.py               # Main application and RAG logic
├── notes.txt              # Your personal knowledge base (input data)
├── knowledge.json         # Auto-generated local vector storage
├── requirements.txt       # Python dependencies (openai, numpy)
├── .gitignore             # Git ignore rules for keys and cache
└── README.md              # Project documentation
