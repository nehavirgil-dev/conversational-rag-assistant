Conversational RAG Assistant

Project Overview
This project implements a Conversational Retrieval-Augmented Generation (RAG) Assistant that combines document retrieval, conversational memory, history-aware retrieval, and tool calling.

The assistant can:

* Answer questions using retrieved context from a knowledge base.
* Remember previous interactions using chat history.
* Handle follow-up questions intelligently.
* Call external tools when required.
* Route queries between retrieval and tool execution.

Features
1. Conversation Memory: The assistant maintains chat history using a Python list.
Example:

User: What is RAG?

User: Can you explain it more?

The assistant uses previous messages to understand that "it" refers to RAG.

2. History-Aware Retrieval: Before retrieval, follow-up questions are rewritten into standalone questions.
Example:

Can you explain it more?

↓

Can you explain RAG in more detail?

This improves retrieval quality and context understanding.

3. Vector Database: FAISS is used as the vector database.

Document chunks are converted into embeddings using HuggingFace Embeddings and stored in FAISS for semantic retrieval.

4. External Tool:
Tool Implemented: get_current_time()
Returns the current system time.

Example:

User: What is the current time?

Assistant: The current time is 12:20:19

5. Routing Logic: The assistant determines whether a query should:

* Use retrieval (RAG)
* Use an external tool

Example:

"What is RAG?" → Retrieval

"What is the current time?" → Tool

Architecture

User Query
↓
Conversation History
↓
Question Rewriting
↓
Routing Logic
├── Retrieval (RAG)
└── Tool Calling
↓
Response

Technologies Used

* Python
* LangChain
* FAISS
* HuggingFace Embeddings
* Jupyter Notebook

Project Structure

conversational-rag-assistant/

├── Conversational_RAG_Assistant.ipynb

├── tools.py

├── README.md

├── requirements.txt

└── screenshots/

How to Run

1. Install dependencies
pip install -r requirements.txt

2. Open the notebook
Conversational_RAG_Assistant.ipynb

3. Run all cells

4. Interact with the assistant

Type:

What is RAG?

or

What is the current time?

Type exit to stop the assistant.
