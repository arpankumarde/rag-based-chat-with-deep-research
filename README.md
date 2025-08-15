# RAG-Based Chat System with Deep Research

A comprehensive Retrieval Augmented Generation (RAG) chat system that enables users to upload multiple document types and interact with their content through both standard chat and advanced deep research capabilities.

## Features

### Multi Format Document Processing

- **Multi-format support**: PDF, PowerPoint (PPT/PPTX), CSV, Excel, Word (DOC/DOCX), and Text files
- **Bulk upload capability**: Process multiple documents simultaneously
- **Advanced text extraction**: Powered by Docling for superior document parsing
- **Intelligent chunking**: Optimized content segmentation for better retrieval
- **Vector embeddings**: Efficient document vectorization using ChromaDB

### Standard Chat

- **Document querying**: Natural language interaction with uploaded documents
- **Contextual responses**: AI-powered answers based on document content powered by Gemini 2.5 Flash
- **Chat history**: Persistent conversation management
- **Source attribution**: Clear references to source documents with page numbers and context

### Deep Research

- **Comprehensive analysis**: Multi-document synthesis and cross-referencing
- **Research reports**: Generate detailed analyses with citations and evidence
- **Topic extraction**: Identify key themes and concepts across document collections
- **Comparative analysis**: Side-by-side document comparison and contrast
- **Citation tracking**: Maintain complete provenance of information sources

## Tech Stack

- **LLM**: Google Gemini 2.5 Flash (Fast, efficient, and cost-effective)
- **Vector Database**: ChromaDB (Local-first vector storage and similarity search)
- **Document Processing**: Docling (Advanced document parsing and structure extraction)
- **Backend**: Python 3.9+
- **Embeddings**: ChromaDB's built-in embedding models with custom configurations

## Installation

### Prerequisites

- Python 3.9 or higher
- pip package manager
- Google AI API key for Gemini access

### Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/arpankumarde/rag-based-chat-with-deep-research
   cd rag-based-chat-with-deep-research
   ```

2. **Create and activate virtual environment**

   ```bash
   python -m venv venv

   # On Windows
   venv\Scripts\activate

   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Environment configuration**
   Create a `.env` file in the root directory:

   ```env
   GOOGLE_API_KEY=your_gemini_api_key_here
   CHROMA_DB_PATH=./chroma_db
   LOG_LEVEL=INFO
   ```

5. **Initialize the system**

   ```bash
   python app.py --init
   ```

## Usage

### Running the Application

Start the RAG chat system:

```bash
python app.py
```

## Architecture Overview

```text
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   CLI Interface │    │     Docling      │    │   ChromaDB      │
│                 │    │    Document      │    │  Vector Store   │
│  - File Upload  │◄──►│    Processor     │◄──►│                 │
│  - Chat Commands│    │                  │    │  - Embeddings   │
│  - Research API │    │  - Advanced OCR  │    │  - Collections  │
└─────────────────┘    │  - Layout Parser │    │  - Metadata     │
         │             │  - Table Extract │    │  - Similarity   │
         │             └──────────────────┘    └─────────────────┘
         ▼                      │                       │
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│  Gemini 2.5     │    │  RAG Pipeline    │    │  Research       │
│  Flash LLM      │    │                  │    │  Engine         │
│                 │◄──►│  - Query Process │◄──►│                 │
│  - Fast Response│    │  - Context Retr  │    │  - Multi-doc    │
│  - Cost Friendly|    │  - Answer Synth  │    │    Analysis     │
│  - JSON Support │    │  - Source Track  │    │  - Report Gen   │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

### Key Components

1. **Docling Document Processor**

   - Advanced PDF parsing with layout preservation
   - Table and image extraction
   - Multi-format document support
   - Metadata extraction and preservation

2. **ChromaDB Vector Store**

   - Local-first vector database
   - Efficient similarity search
   - Document collections management
   - Metadata filtering capabilities

3. **Gemini 2.5 Flash Integration**

   - Fast response times
   - Cost-effective operations
   - JSON mode support for structured outputs
   - Context-aware responses

4. **RAG Pipeline**

   - Query preprocessing and expansion
   - Semantic similarity search
   - Context ranking and filtering
   - Response synthesis with citations

5. **Research Engine**
   - Cross-document analysis
   - Topic modeling and extraction
   - Comparative document analysis
   - Research report generation

## Performance Optimization

### Document Processing

- **Batch processing**: Process multiple documents simultaneously
- **Caching**: Cache processed documents to avoid reprocessing
- **Incremental updates**: Only process new or modified documents

### Vector Database

- **Index optimization**: Regular index maintenance for optimal search performance
- **Memory management**: Efficient embedding storage and retrieval
- **Query optimization**: Smart query preprocessing and filtering

### LLM Usage

- **Context optimization**: Intelligent context selection to minimize token usage
- **Response caching**: Cache frequently requested information
- **Batch processing**: Group similar queries for efficient processing

## Future Enhancements

- [ ] Multi-language document support
- [ ] Real-time document collaboration
- [ ] Advanced visualization dashboard
- [ ] Custom embedding model training
- [ ] Integration with external knowledge bases
- [ ] Advanced citation and reference management

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes with proper tests
4. Commit your changes (`git commit -m 'Add amazing feature'`)
5. Push to the branch (`git push origin feature/amazing-feature`)
6. Open a Pull Request

## Technical Choices & Rationale

### Why Gemini 2.5 Flash?

- **Speed**: Optimized for fast response times
- **Cost-effectiveness**: Balanced performance-to-cost ratio
- **JSON support**: Native structured output support
- **Context length**: Large context window for comprehensive analysis

### Why ChromaDB?

- **Local-first**: No external dependencies for basic operations
- **Simplicity**: Easy setup and maintenance
- **Performance**: Efficient similarity search capabilities
- **Flexibility**: Support for multiple embedding models

### Why Docling?

- **Advanced parsing**: Superior document structure extraction
- **Multi-format support**: Comprehensive file type coverage
- **Layout preservation**: Maintains document formatting and structure
- **Metadata extraction**: Rich document metadata for better retrieval

## Acknowledgments

- Google AI for Gemini LLM capabilities
- ChromaDB team for the excellent vector database
- Docling contributors for advanced document processing
- The open-source community for various supporting libraries
