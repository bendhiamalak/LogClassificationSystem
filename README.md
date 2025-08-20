# Log Classification System 🚀
An intelligent log classification system that combines Regex, Machine Learning (BERT + Logistic Regression), and LLMs to automatically classify log messages.

This project follows a hybrid approach:
- Regex first → fast classification for known patterns.
- ML (SentenceTransformer + Logistic Regression) → generalizes classification when regex fails.
- LLM fallback (Groq API, LLaMA-3) → for ambiguous or domain-specific logs (e.g., LegacyCRM).
- Served via FastAPI API for easy integration.

### Features
-✅ Regex-based rules.
-✅ Transformer embeddings (all-MiniLM-L6-v2) for semantic understanding of logs.
-✅ Logistic Regression classifier trained on embeddings.
-✅ LLM integration (LLaMA-3 via Groq API) for special cases.
-✅ REST API (FastAPI) to classify logs from CSV input.
-✅ Modular design (processor_regex.py, processor_bert.py, processor_llm.py).

### Tech Stack
- Python 
- FastAPI & Uvicorn (API backend)
- scikit-learn (Logistic Regression)
- SentenceTransformers (Embeddings)
- Groq API (LLM)
- pandas, numpy (data handling)


### Installation

Clone the repository:
bash```
git clone https://github.com/bendhia/Logclassificationsystem.git
cd LogClassificationSystem
```

Create and activate a virtual environment:
bash```
python -m venv venv
venv\Scripts\activate      # Windows
```

Install dependencies:
bash```
pip install -r requirements.txt
```

### Usage
Run the API locally
bash```
uvicorn app:app --reload
```

API Endpoint

POST /classify/

Input: CSV file with columns source and log_message.
Output: Classified CSV with extra column target_label.


