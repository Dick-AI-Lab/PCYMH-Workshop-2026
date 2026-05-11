# PCYMH-Workshop-2026: AI for Mental Health Applications

**A Practical Introduction to AI for Clinicians, Researchers & Trainees**
PCYMH 2026 · May 11, 2026 · National Arts Centre, Ottawa, Ontario

---

## Launch Notebooks in Google Colab

| # | Notebook | Topic | Open |
|---|----------|-------|------|
| 1 | ML Foundations | Build an ASD screening classifier from behavioural assessment data | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dick-AI-Lab/PCYMH-Workshop-2026/blob/main/workshop/notebooks/01_ml_foundations.ipynb) |
| 2 | Explainability & SHAP | Explain model predictions and audit for bias using SHAP | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dick-AI-Lab/PCYMH-Workshop-2026/blob/main/workshop/notebooks/02_explainability_shap.ipynb) |
| 3 | Privacy-Preserving LLMs | Run local LLMs for summarization, extraction, and de-identification | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dick-AI-Lab/PCYMH-Workshop-2026/blob/main/workshop/notebooks/03_privacy_llm_ollama.ipynb) |

> **No installation required.** All notebooks run in your browser via Google Colab. A Google account is the only prerequisite.

---

## About the Workshop

This 75-minute hands-on workshop introduces AI and machine learning to mental health clinicians, researchers, and trainees — no prior coding experience needed. Participants work through three live Jupyter notebooks alongside a slide-based presentation that covers theory, ethics, and clinical context.

### What You Will Learn

| Section | Topics |
|---------|--------|
| AI Landscape | Why AI now, terminology (AI/ML/DL/LLMs), applications in healthcare and mental health |
| ML Fundamentals | Supervised learning pipeline, train/test split, overfitting, evaluation metrics |
| Explainability & Ethics | SHAP values, global vs. local explanations, bias auditing, fairness |
| Privacy-Preserving AI | Local LLMs via Ollama, clinical text summarization, de-identification |
| Clinical Integration | Implementation gap, 5-step integration roadmap, responsible AI framework |

### Case Study

Throughout the workshop we use the **ABIDE dataset** (Autism Brain Imaging Data Exchange) to build an ASD screening classifier from behavioural assessments — a real-world example directly translatable to perinatal and youth mental health screening contexts.

---

## Repository Structure

```
PCYMH-Workshop-2026/
├── workshop/
│   ├── notebooks/
│   │   ├── 01_ml_foundations.ipynb        # ~15-20 min hands-on
│   │   ├── 02_explainability_shap.ipynb   # ~10-15 min hands-on
│   │   └── 03_privacy_llm_ollama.ipynb    # ~10 min hands-on
│   ├── presentation/
│   │   └── index.html                     # Standalone slide deck (open in browser)
│   ├── facilitator_guide.md               # Presenter notes and timing guide
│   └── README.md
└── README.md
```

---

## How to Use

### At the Workshop
1. Scan the QR code displayed on the title slide, **or** navigate to this repository.
2. Click the **Open in Colab** button for **Notebook 1** above.
3. Sign in with a Google account and run cells as directed by the facilitators.

### Self-Directed / After the Workshop
- Open notebooks in order (01 → 02 → 03); each builds on the previous.
- The slide deck (`workshop/presentation/index.html`) can be opened locally in any browser — no server required.
- Press `?` while viewing the slides for keyboard shortcuts; `S` to toggle speaker notes.

---

## Presenters

| Name | Role | Institution |
|------|------|-------------|
| **Kevin Dick** | AI Data Scientist & Principal Investigator | BORN Ontario · CHEO-RI |
| **Alibek Kruglikov** | Postdoctoral Fellow | Dick AI Lab, CHEO-RI |
| **Youssef Megahed** | AI Analyst | Dick AI Lab, BORN Ontario |

---

## License

Materials released under the [MIT License](LICENSE). Reuse and adaptation encouraged with attribution.

**Dick AI Lab** · BORN Ontario · CHEO Research Institute
