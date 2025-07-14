# docIQ
📄 Smart Research Assistant
🚀 AI-powered, fully local GenAI app that reads research papers or text documents, answers questions, and quizzes you — without using any paid API key.

Built with transformers, sentence-transformers, faiss, and a clean Gradio interface.

✨ Features
✅ Upload PDF or TXT documents
✅ Auto-generate a concise summary (≤150 words)
✅ Ask Anything – free-form question answering grounded in your document
✅ Challenge Me – auto-generates 3 logic/comprehension questions and checks your answers
✅ Justifies every answer with references from your document
✅ Runs completely offline (no OpenAI key or external API)

🧠 How it works
Splits the uploaded document into ~500-word chunks

Encodes chunks into embeddings with all-MiniLM-L6-v2

Indexes them with faiss for fast retrieval

For Q&A:

Retrieves the best matching chunk

Answers using distilbert-base-cased-distilled-squad

Summarizes first ~1024 words with facebook/bart-large-cnn

Challenge mode:

Auto-generates 3 questions based on sampled chunks

Compares your answers to model’s answers & gives feedback

🏗 Tech Stack
Task	Model / Library
Summarization	facebook/bart-large-cnn
Question Answering	distilbert-base-cased-distilled-squad
Embeddings	sentence-transformers: all-MiniLM-L6-v2
Semantic Search	faiss-cpu
UI	Gradio

📦 Project Structure
bash
Copy
Edit
smart-research-assistant/
├── app.py                # Main Gradio app
├── requirements.txt      # Python dependencies
└── README.md             # You're reading it!
(You can add modules like rag_engine.py or summarizer.py if you modularize later.)

⚙️ Setup & Run
1️⃣ Clone & install:

bash
Copy
Edit
git clone https://github.com/yourusername/smart-research-assistant.git
cd smart-research-assistant
pip install -r requirements.txt
2️⃣ Launch app:

bash
Copy
Edit
python app.py
✅ Gradio will open a local link (and optionally a share link).

📄 Requirements
See requirements.txt:

txt
Copy
Edit
gradio==4.25.0
pdfplumber==0.10.2
transformers==4.41.1
sentence-transformers==2.7.0
faiss-cpu==1.7.4
torch>=2.0.0
numpy>=1.21.0
⚠ Limitations
Only works on text PDFs (not scanned images).

No multi-turn conversation memory (yet).

Runs on CPU; large docs may be slower (GPU recommended).

💡 Future Enhancements (ideas)
OCR support for scanned PDFs

Multi-turn dialogue & context memory

Export Q&A or quiz results to PDF

Highlight answer span in document

Custom question generation modes

📜 License
Free for educational and non-commercial use.

❤️ Why this?
Because students, researchers, and developers deserve

local, private & explainable AI tools
without expensive API keys or data leaving your machine.

Built with Python, Hugging Face, and a lot of ☕.
Enjoy exploring your documents smarter! 🌱

##Working Share of ScreenShots
<img width="1516" height="482" alt="Screenshot 2025-07-14 093025" src="https://github.com/user-attachments/assets/97486602-4000-4822-aa21-fc8290b7862c" />
<img width="1465" height="409" alt="Screenshot 2025-07-14 095054" src="https://github.com/user-attachments/assets/4af35325-caed-46c9-87c9-119f5bfd054e" />
<img width="1465" height="408" alt="Ask Anything" src="https://github.com/user-attachments/assets/9d8b33ad-57a0-4906-87f2-7334e1e652c7" />
<img width="1465" height="408" alt="Ask Anything" src="https://github.com/user-attachments/assets/3873df1e-7062-4033-a47f-4543d9bf2434" />
<img width="1517" height="476" alt="Generate Question" src="https://github.com/user-attachments/assets/a94c6276-1233-4ac3-bf54-7768f687f7eb" />
<img width="1503" height="441" alt="Screenshot 2025-07-14 095240" src="https://github.com/user-attachments/assets/791ccdd9-9ea6-406b-b4c4-3355379b17e9" />
<img width="1502" height="441" alt="Answer Reasoning" src="https://github.com/user-attachments/assets/e5e234bc-7828-4fbf-a001-b494518842db" />






