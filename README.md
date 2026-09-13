# SmartStudy

SmartStudy is a local document Q&A assistant. Upload a PDF, ask a question, and get an answer grounded in that document.

## Important Requirements & Limitations
- **PDF Format:** The uploaded PDF must contain plain, machine-readable text. **Handwritten notes or scanned images of text are not supported.**
- **Strict Grounding:** The chatbot strictly answers questions based *only* on the uploaded PDF. If a user asks a question unrelated to the document, the LLM will not predict or invent an answer; it will explicitly state that the information is not in the notes.

## Features
- Upload PDF notes via drag-and-drop or file picker
- Ask questions grounded in the uploaded document
- RAG pipeline: chunking, embeddings, and semantic search
- Persistent chat history (SQLite)
- One-click chat and document reset

## Tech Stack
- **Backend:** Python, FastAPI
- **Frontend:** HTML, CSS, JavaScript
- **LLM:** Groq API
- **Embeddings:** `fastembed` (BAAI/bge-small-en-v1.5)
- **Vector store:** ChromaDB
- **Chat history:** SQLite

## How It Works
1. **Upload:** PDF text is extracted using `pypdf`.
2. **Chunk:** Text is split into overlapping word chunks.
3. **Embed:** Chunks are embedded and stored in ChromaDB.
4. **Ask:** The user's question is embedded and similar chunks are retrieved.
5. **Answer:** Retrieved notes are sent to the LLM as context to generate an answer.

## Setup & Running in an IDE
1. **Clone the repository:**
   ```bash
   git clone https://github.com/HARSHA0github/SmartStudy.git
   cd SmartStudy
   ```
2. **Open the `SmartStudy` folder** in your preferred IDE (e.g., VS Code, PyCharm).
3. **Create a virtual environment and install dependencies** from the IDE terminal:
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   
   pip install -r requirements.txt
   ```
4. **Create a `.env` file** in the project root:
   ```env
   GROQ_API_KEY=your_groq_api_key_here
   ```
5. **Run the application:**
   ```bash
   python run.py
   ```
6. **Access the App:** Open your browser and navigate to http://127.0.0.1:8000

## Project Structure
```text
SmartStudy/
├── app/
│   ├── main.py
│   ├── llm.py
│   ├── rag.py
│   └── database.py
├── templates/
│   └── index.html
├── static/
│   ├── style.css
│   └── script.js
├── run.py
├── requirements.txt
└── .gitignore
```

## Patent & Rights Transfer
All patents, copyrights, and intellectual property rights embedded within this project have been fully transferred from HARSHA0github. This project and its code are released for unrestricted use, modification, and distribution.
