# Healthcare Hybrid Retrieval QA

**CAI Assignment PS1** — Conversational question-answering over the MedQuAD healthcare dataset using hybrid search.

## What it does

Combines sparse and dense retrieval with reciprocal rank fusion to answer healthcare questions conversationally:

- **Sparse retrieval** — BM25 (`rank_bm25`)
- **Dense retrieval** — Sentence Transformers (`all-MiniLM-L6-v2`, ~90 MB, auto-downloaded on first run)
- **Hybrid fusion** — Reciprocal Rank Fusion (RRF, k=60)
- **Conversational QA** — multi-turn pipeline with domain filtering and a medical disclaimer
- **Evaluation** — Precision@K, Recall@K, MRR, HitRate@K on 12 healthcare queries

## Files

| File | Description |
|------|-------------|
| `healthcare_hybrid_retrieval_medquad.ipynb` | Complete executable notebook (all 6 tasks + technical report) |
| `healthcare_hybrid_retrieval_medquad.html` | HTML export with outputs embedded |
| `requirements.txt` | Python dependencies |

## Data

Requires **`medquad.csv`** — not included in this repo due to size (23 MB).

Obtain from [MedQuAD on GitHub](https://github.com/abachaa/MedQuAD) and export the `question`, `answer`, `source`, `focus_area` fields to a CSV named `medquad.csv`. Place it in the same folder as the notebook.

## Setup

```bash
pip install -r requirements.txt
jupyter notebook healthcare_hybrid_retrieval_medquad.ipynb
```

Run cells top-to-bottom (Cell 1 → Cell 16). Cell 2 installs additional dependencies if needed.

> **Medical Disclaimer:** This system is for educational purposes only and is not a substitute for professional medical advice, diagnosis, or treatment.
