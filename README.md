# MyVision: Enhancing Academic Educational Guidance with Retrieval-Augmented Generation

MyVision is a Retrieval-Augmented Generation (RAG) system designed to provide comprehensive academic educational guidance. This project aims to assist prospective university students by offering detailed information about 70 university courses across two universities, as well as information about university libraries.

## Project Overview
This Jupyter notebook demonstrates the construction of a RAG system capable of answering questions related to university courses and libraries. The system leverages a combination of advanced natural language processing techniques and efficient data retrieval mechanisms to provide accurate and relevant information.

## Features
- Extensive Knowledge Base: Covers 70 university courses from two different universities and includes information about their respective libraries.
- Retrieval-Augmented Generation: Combines the power of large language models (LLMs) with a robust retrieval mechanism to generate informative answers based on specific documents.
- Custom Embedding Model: Utilizes the BAAI/bge-m3 HuggingFace embedding model for converting text into semantically rich vector representations, ensuring accurate similarity search.
- Hybrid Indexing: Employs a combination of BM25 for sparse retrieval and Chroma for dense retrieval to maximize information retrieval effectiveness. (Note: Currently, only BM25 is actively used due to an issue with QueryFusionRetriever).
- Detailed Document Parsing: Uses MarkdownNodeParser to split documents into smaller, context-aware chunks (nodes) while preserving relationships and metadata.
- Evaluation Framework: Includes a custom evaluation setup to assess the relevance and correctness of generated answers and retrieved contexts.

## Setup
To run this project, you'll need a Google Colab instance with GPU support for efficient embedding generation.

1. Connect to Google Drive
The project accesses cached data and source documents from Google Drive.

2. Install Dependencies
Install the necessary Python packages.

3. Asynchronous Support
Enable nest_asyncio for asynchronous API calls.

4. Groq Client Setup
This project uses Groq as the LLM API vendor. Your Groq API key should be set up (preferably via Colab secrets).

5. Initialize Embedding Model
Configure the HuggingFace embedding model. The BAAI/bge-m3 model is used for its performance with English text.

## Usage
### Loading and Ingestion
Documents are loaded and parsed with custom metadata to enhance retrieval. The MarkdownNodeParser is used for effective chunking.

### Indexing, Embedding, and Storing
The processed nodes are indexed and stored using ChromaDB for vector storage and a simple document store for node persistence.

### Retrieval
The BM25 retriever is used to fetch relevant documents based on user queries.

### Evaluation
The project includes an evaluation process using a set of 71 pre-generated question-answer pairs. The llm_70b (Llama3-70b) is used as an expert evaluation system to judge the relevance and correctness of the RAG's generated answers and the retrieved context. The results are saved to a CSV file (toreview.csv) and text files (evaluation2.txt, context2.txt).

### More Information
You can find more detailed information and raw data in the `data` folder of this repository. The results of the evaluation can be found in the `evaluation` folder.

## Authors
- Samuele Mazzei
- Lorenzo Zambrotto
- Gabriele Tealdo
- Alberto Macagno
- Alessio Palmero Aprosio
