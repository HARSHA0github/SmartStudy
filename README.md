SmartStudy

SmartStudy is a local document Q&A assistant. Upload a PDF, ask a question, and get an answer grounded in that document.

Features
- Upload PDF notes via drag-and-drop or file picker
- Ask questions grounded in the uploaded document
- RAG pipeline: chunking, embeddings, and semantic search
- Persistent chat history (SQLite)
- One-click chat and document reset

Tech Stack
- Backend: Python, FastAPI
- Frontend: HTML, CSS, JavaScript
- LLM: Groq API
- Embeddings: fastembed (BAAI/bge-small-en-v1.5)
- Vector store: ChromaDB
- Chat history: SQLite

How It Works
1. Upload — PDF text is extracted with pypdf
2. Chunk — text is split into overlapping word chunks
3. Embed — chunks are stored in ChromaDB
4. Ask — the question is embedded and similar chunks are retrieved
5. Answer — retrieved notes are sent to the LLM as context

Project Structure
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

Setup & Running in an IDE
1. Clone the repository:
   ```bash
   git clone https://github.com/HARSHAOgithub/SmartStudy.git
   cd SmartStudy
   ```
2. Open the `SmartStudy` folder in your preferred IDE (e.g., VS Code, PyCharm).
3. Create a virtual environment and install dependencies from the IDE terminal:
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   
   pip install -r requirements.txt
   ```
4. Create a `.env` file in the project root:
   ```env
   GROQ_API_KEY=your_groq_api_key_here
   ```
5. Run the application:
   ```bash
   python run.py
   ```
6. Open your browser and navigate to http://127.0.0.1:8000

Patent & Rights Transfer
All patents, copyrights, and intellectual property rights embedded within this project have been fully transferred from HARSHAOgithub. This project and its code are released for unrestricted use, modification, and distribution.
