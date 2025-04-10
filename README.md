
## 📚 Project Title
**Automated YouTube Transcript Summarization and Question-Answering System using Transformer Models**

## 🎯 Objective
To develop an automated system that:
- Summarizes educational YouTube videos using state-of-the-art transformer models (BART, T5, Pegasus).
- Evaluates summary quality using metrics like ROUGE, BERTScore, and cosine similarity.
- Builds a chatbot that answers user queries based on the best available summary per video.

## 🧠 Motivation
Educational content on YouTube is vast and unstructured. Students often seek quick insights or answers without watching full videos. This project helps bridge that gap using summarization and question-answering capabilities.

---

## 📁 Dataset
- **Source:** YouTube video transcripts extracted using the YouTube Transcript API.
- **Size:** 902 videos from domains such as AI, ML, DL, Cybersecurity, Blockchain, and more.
- **Format:** JSON, where each entry includes video ID, title, transcript, and model-generated summaries.

---

## 🔧 Methodology

### 📥 Data Collection
- Used `YouTubeTranscriptApi` to extract transcripts.
- Each transcript saved with its corresponding metadata (video ID, title, length).

### 🧹 Preprocessing
- Removed special characters, timestamps, non-ASCII text.
- Performed sentence splitting for model compatibility.

### 🤖 Summarization
- Models used:
  - BART
  - Pegasus
  - T5
- Each model generates summaries for every transcript.

### 📊 Evaluation
- Metrics:
  - **ROUGE** (ROUGE-1, ROUGE-2, ROUGE-L)
  - **BERTScore**
  - **Cosine Similarity** using Sentence Transformers
- Best summary selected per video based on average scores.

### 📦 Best Summary Generation
- Created a `best_video.json` file that stores:
  - The best-performing model.
  - Summary text.
  - Evaluation scores.

### 💬 Q&A Chatbot
- User enters a query.
- Chatbot uses the best summary to generate answers using OpenAI’s LLM.
- Summarized knowledge base ensures concise and relevant responses.

---

## 🔁 Methodology Flowchart

![Methodology Flowchart](.\methodology_flowchart.png)

---

## 🧪 Tools and Technologies
- Python
- Transformers (HuggingFace)
- Scikit-learn
- Spacy
- SentenceTransformers
- BERTScore
- OpenAI API
- Google Colab

---

## 📈 Results
- 3 Models compared across 902 videos.
- `best_video.json` created with best summary per video.
- Chatbot answers validated for relevance and accuracy.
- Insightful video comparisons available in `video_comparison.json`.

---

## 💡 Future Work
- Incorporate multilingual transcripts.
- Extend chatbot capabilities to handle longer conversations.
- Integrate with a frontend UI for a better user experience.

## 📋 Summary

This project introduces an end-to-end framework that leverages Large Language Models (LLMs) to automatically summarize YouTube educational videos and build a context-aware Q&A chatbot. Transcripts from 902 YouTube videos were collected, preprocessed, and summarized using three transformer models: **BART**, **Pegasus**, and **T5**. A multi-metric evaluation strategy based on **ROUGE**, **BERTScore**, and **Cosine Similarity** was applied to identify the best summary per video.

The best-performing summaries were then indexed using a hybrid **FAISS + BM25** search technique, and used to power a chatbot that can answer user queries using the **T5 model**. The system is lightweight, domain-agnostic, and highly scalable — aimed at assisting students and self-learners in consuming educational content more efficiently.


