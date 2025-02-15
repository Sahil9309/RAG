# **RAG-Based PDF Question Answering System**

**Overview**
This project implements a **Retrieval-Augmented Generation (RAG) System** that allows users to extract insights from PDF documents by querying them using natural language. The system processes PDFs, extracts text, embeds it into a vector store, retrieves relevant information, and generates answers using an LLM.

**Features**
1.**Multi-language Text Extraction**: Extracts text from digital and scanned PDFs using OCR with multiple language support (English, Hindi, Bengali, Simplified Chinese).
2. **Efficient Text Chunking**: Uses **RecursiveCharacterTextSplitter** to divide the text into semantically meaningful chunks.
3. **Semantic Search with FAISS**: Stores embeddings in a FAISS index for fast and efficient similarity search.
4. **LLM-Based Answer Generation**: Utilizes the **Flan-T5 model** to generate human-like answers based on retrieved context.
5. **Cosine Similarity Reranking**: Ensures that the most relevant text chunks are used for answering queries.

**Installation**
```bash
pip install pymupdf pytesseract pillow langchain sentence-transformers faiss-cpu transformers torch torchvision torchaudio
```

**Usage**
### **1. Extract Text from a PDF:**
```python
text = extract_text_from_pdf("path/to/your/file.pdf")
```

**2. Process Text into Chunks:**
```python
chunks = process_text(text)
```

**3. Create Vector Store:**
```python
index, embeddings = create_vector_store(chunks)
```
**4. Initialize RAG System:**
```python
rag = RAGSystem(index, embeddings, chunks)
```
**5. Query the Document:**
```python
answer = rag.query("What is the core message of the book?")
print(answer)
```

**File Structure**
```
project/
│── main.py  # Main script for running the system
│── README.md  # Documentation
│── requirements.txt  # List of required packages
│── data/
│   ├── sample.pdf  # Example PDF file
```


