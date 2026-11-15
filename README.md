# Intelligent Document Question Answering System using RAG & LLMs

An AI-powered Intelligent Document Question Answering System built using **Retrieval-Augmented Generation (RAG)** and Large Language Models (LLMs). The application allows users to upload PDF documents and ask questions based on their content. It retrieves relevant information using FAISS vector search and generates context-aware answers using Llama 3.2 through Ollama.

## 🚀 Features

- **PDF Upload:** Upload PDF documents through an interactive Streamlit interface.
- **Text Extraction:** Extract readable text from PDF files using PyPDF2.
- **Text Chunking:** Split extracted text into smaller overlapping chunks for efficient retrieval.
- **Embedding Generation:** Generate vector embeddings using Sentence Transformers.
- **FAISS Vector Database:** Store and search document embeddings efficiently.
- **Semantic Search:** Retrieve the most relevant document chunks based on user questions.
- **LLM Integration:** Use Llama 3.2 through Ollama to generate context-aware answers.
- **Context-Based Responses:** Generate answers using retrieved document content rather than outside knowledge.
- **Interactive Interface:** View extracted text, retrieved context, and generated answers using Streamlit.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Streamlit | Interactive web application |
| PyPDF2 | PDF text extraction |
| Sentence Transformers | Text embedding generation |
| FAISS | Vector database and similarity search |
| Ollama | Local LLM integration |
| Llama 3.2 (1B) | Context-aware answer generation |
| NumPy | Numerical operations |
| Requests | Communication with Ollama API |

## 🧠 RAG Architecture

The application follows a Retrieval-Augmented Generation workflow:

1. **PDF Upload:** User uploads a PDF document.
2. **Text Extraction:** Extract text from PDF pages using PyPDF2.
3. **Text Chunking:** Divide extracted text into chunks of 500 characters with 100 characters of overlap.
4. **Embedding Generation:** Convert text chunks into numerical vectors using the `all-MiniLM-L6-v2` Sentence Transformer model.
5. **Vector Storage:** Store embeddings in a FAISS `IndexFlatL2` index.
6. **Question Embedding:** Convert the user's question into a vector embedding.
7. **Similarity Search:** Retrieve the top 3 relevant chunks from FAISS.
8. **Context Preparation:** Combine retrieved chunks with the user's question.
9. **Answer Generation:** Send the context and question to Llama 3.2 through Ollama.
10. **Display Results:** Show the generated answer in the Streamlit application.

## 📂 Project Structure

```text
Intelligent-Document-Question-Answering-System/
│
├── app.py                 # Main Streamlit application
├── README.md              # Project documentation
└── requirements.txt       # Python dependencies
```

*Note: `app.py` is the suggested filename for your main Python script. Update it if your actual filename is different.*

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

```bash
cd Intelligent-Document-Question-Answering-System
```

### 2. Install Dependencies

```bash
pip install streamlit PyPDF2 faiss-cpu numpy requests sentence-transformers
```

### 3. Install Ollama

Download and install Ollama:

https://ollama.com/

### 4. Download the Llama 3.2 Model

Open a terminal and execute:

```bash
ollama pull llama3.2:1b
```

Ensure Ollama is running locally. The application communicates with its API at:

```text
http://localhost:11434/api/generate
```

### 5. Run the Application

```bash
streamlit run app.py
```

The Streamlit application will open in your browser.

## 💻 How to Use

1. Launch the Streamlit application.
2. Open the **Upload PDF** tab.
3. Upload a readable PDF document.
4. Wait for text extraction, chunking, embedding generation, and FAISS indexing.
5. Enter a question related to the uploaded document.
6. View the retrieved relevant context.
7. Get an AI-generated answer based on the PDF content.

## 📚 Concepts Implemented

- Retrieval-Augmented Generation (RAG)
- Large Language Models (LLMs)
- Natural Language Processing (NLP)
- Text Embeddings
- Vector Databases
- Semantic Search
- Similarity Search
- Prompt Engineering
- PDF Processing
- Local LLM Integration

## 🔮 Future Enhancements

- Support for multiple PDF documents.
- Conversation history and follow-up questions.
- Chat-based interface.
- OCR support for scanned PDF documents.
- Downloadable question-answering reports.

## 👩‍💻 Author

**Diksha Kadu Vispute**

Computer Engineering Student | Python | AI/ML | Generative AI

GitHub: [DikshaVispute](https://github.com/DikshaVispute)
