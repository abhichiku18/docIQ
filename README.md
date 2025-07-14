# 📚 docIQ – Smart Research Assistant
AI-powered, fully local GenAI app that helps you explore, understand, and quiz yourself on research papers or text documents — completely offline, **without any paid API key**.

Built with Hugging Face Transformers, Sentence-Transformers, Faiss, and Gradio.

<!-- Optional: Add video demo link or GIF here -->
> 🎥 **See the full video demo here:** [Video Link](https://youtu.be/tAq5Whcd47U?si=bGngQe-TYxz8fxmE)

---

## ✨ Features
✅ Upload and analyze PDF or TXT documents  
✅ Auto-generate a concise summary (≤150 words)  
✅ Ask Anything – free-form question answering grounded in your document  
✅ Challenge Me – generates 3 comprehension questions & checks your answers  
✅ Justifies answers with references from the uploaded document  
✅ Runs fully offline on your machine (no OpenAI key, no external API)

---

## ⚙️ How It Works
1. Splits document into ~500-word chunks  
2. Creates embeddings with **all-MiniLM-L6-v2**  
3. Indexes them using **Faiss** for fast retrieval  
4. For Q&A: retrieves top chunk & answers with **distilbert-base-cased-distilled-squad**  
5. Summarizes first ~1024 words with **facebook/bart-large-cnn**  
6. Challenge Mode: auto-generates questions & compares your answers

---

## 🏗 Tech Stack

| Task                | Model / Library                                       |
|--------------------|------------------------------------------------------|
| Summarization      | `facebook/bart-large-cnn`                             |
| Question Answering | `distilbert-base-cased-distilled-squad`               |
| Embeddings         | `sentence-transformers: all-MiniLM-L6-v2`             |
| Semantic Search    | `faiss-cpu`                                          |
| UI                 | `Gradio`                                             |

---

## 📦 Project Structure
smart-research-assistant/
├── app.py # Main Gradio app
├── requirements.txt # Python dependencies
└── README.md # Project documentation

1️⃣ Clone and install:
```bash
git clone https://github.com/abhichiku18/docIQ.git
cd docIQ
pip install -r requirements.txt

2️⃣ Launch app:
python app.py

## requirements.txt
gradio==4.25.0
pdfplumber==0.10.2
transformers==4.41.1
sentence-transformers==2.7.0
faiss-cpu==1.7.4
torch>=2.0.0
numpy>=1.21.0

⚠️ Limitations
i. Works only on text-based PDFs (not scanned images)
ii. No multi-turn conversation memory (yet)
iii. Runs on CPU; large documents may be slower (GPU recommended)

💡 Future Enhancements
OCR support for scanned PDFs
Multi-turn dialogue & conversation memory
Export Q&A or quiz results to PDF
Highlight answer span in document
Custom question generation modes

## Screenshots
<img width="1516" height="482" alt="First UI " src="https://github.com/user-attachments/assets/3257294a-53c0-490e-b376-ccbb2512101e" />
<img width="1517" height="335" alt="Summary " src="https://github.com/user-attachments/assets/d6ba3a60-926c-47c6-9ddc-622243587e62" />
<img width="1465" height="408" alt="Ask Anything" src="https://github.com/user-attachments/assets/19b5715b-da3d-4d27-97e2-3cbe9024be5d" />
<img width="1517" height="476" alt="Generate Question" src="https://github.com/user-attachments/assets/b66af17f-d3a8-4a53-9ccc-e6ad484afdd5" />
<img width="1571" height="508" alt="Answer Response" src="https://github.com/user-attachments/assets/67945485-641e-4b55-b4c8-d105bea32620" />













