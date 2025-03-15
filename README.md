# RAG Implementation with LlamaIndex

This project implements a Retrieval-Augmented Generation (RAG) system using LlamaIndex, allowing for efficient document processing and question-answering capabilities over both unstructured documents and structured SQL data.

## Project Structure

```
├── content/              # Directory for source documents
├── extracted_content/    # Directory for processed documents
├── vector_db/           # Vector database storage
├── database/            # SQLite database storage
├── prepare_vector_db.ipynb  # Notebook for preparing vector database
├── rag.ipynb            # Main RAG implementation notebook
├── .env                 # Environment variables (create from .env.example)
└── .env.example         # Example environment variable template
```

## Directory Setup

The project automatically creates and manages several directories during execution:

- `extracted_content/`: Created automatically when running `prepare_vector_db.ipynb`. Contains subdirectories for:
  - `images/`: Extracted images from the PDF
  - `tables/`: Extracted table data in structured format
  - `table_images/`: Visual representations of extracted tables
  - `text/`: Extracted text content
- `vector_db/`: Contains the vector database for document embeddings

You don't need to create these directories manually - they will be created automatically when running the notebooks.

## Setup

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set up environment variables:
   - Copy `.env.example` to `.env`:
     ```bash
     cp .env.example .env
     ```
   - Edit `.env` with your configuration:
     ```
     OPENAI_API_KEY="your-api-key-here"
     PDF_FILE_PATH="content/wiki.pdf"
     SQL_DATABASE_PATH="./database/olist.sqlite"
     ```
4. Place your documents in the `content/` directory
5. Place your SQLite database in the `database/` directory (Download sample database from [Kaggle: E-commerce Dataset by Olist as an SQLite Database](https://www.kaggle.com/datasets/terencicp/e-commerce-dataset-by-olist-as-an-sqlite-database))

## Usage

1. First, run `prepare_vector_db.ipynb` to process your documents and create the vector database
2. Then use `rag.ipynb` to interact with the RAG system and ask questions about your documents

## Features

- Document processing and chunking
- Vector store implementation using Chroma
- Integration with OpenAI's language models
- SQL database support for structured data
- Hybrid search capabilities

## Requirements

- Python 3.8+
- OpenAI API key
- See requirements.txt for full dependency list

## Environment Variables

Required environment variables in `.env`:
- `OPENAI_API_KEY`: Your OpenAI API key

## License

This project is licensed under the MIT License. 