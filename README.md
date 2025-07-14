# 📚 docIQ – Smart Research Assistant
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Offline](https://img.shields.io/badge/Offline-%F0%9F%9A%AB%20No%20API-red)

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

## 📸 Screenshots

<p align="center">
  <img src="images/overview.png" alt="Overview" width="80%" />
</p>

<p align="center">
  <img src="images/first_ui.png" alt="First UI" width="80%" />
</p>

<p align="center">
  <img src="images/summary.png" alt="Summary" width="80%" />
</p>

<p align="center">
  <img src="images/ask_anything.png" alt="Ask Anything" width="80%" />
</p>

<p align="center">
  <img src="images/generate_question.png" alt="Generate Question" width="80%" />
</p>

<p align="center">
  <img src="images/answer_response.png" alt="Answer Response" width="80%" />
</p>

<p align="center">
  <img src="images/answer_response.png" alt="Answer Response" width="80%" />
</p>

