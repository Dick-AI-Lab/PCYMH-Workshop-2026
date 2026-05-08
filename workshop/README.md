# Practical Introduction to AI for Mental Health Applications
## Workshop Materials — PCYMH 2026

**Duration:** 75 minutes | **Format:** Slides + hands-on Python notebooks | **Prerequisites:** None

---

## Overview

This workshop provides a practical, hands-on introduction to artificial intelligence and machine learning for mental health research. Participants work through three beginner-friendly Python notebooks covering the complete clinical AI workflow: building a prediction model, explaining its decisions with SHAP, and applying privacy-preserving LLMs to clinical text.

### Learning Objectives
1. Understand core AI/ML concepts and how they apply to mental health research workflows
2. Develop hands-on skills by running models, generating SHAP explanations, and using local LLMs for clinical NLP tasks

---

## Quick Start — Open Notebooks in Google Colab

No installation required. Click a link to open directly in your browser.

| # | Notebook | Topic | Link | Time |
|---|----------|-------|------|------|
| 1 | ML Foundations | Build & evaluate a classifier on ASD phenotypic data | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/[USERNAME]/[REPO]/blob/main/workshop/notebooks/01_ml_foundations.ipynb) | ~25 min |
| 2 | Explainability & SHAP | Explain model decisions with SHAP values | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/[USERNAME]/[REPO]/blob/main/workshop/notebooks/02_explainability_shap.ipynb) | ~20 min |
| 3 | Privacy-Preserving LLMs | Summarize, extract, and de-identify clinical notes locally | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/[USERNAME]/[REPO]/blob/main/workshop/notebooks/03_privacy_llm_ollama.ipynb) | ~20 min |

### How to Run a Notebook
1. Click a Colab link above (Google account required — free)
2. Click **Runtime → Run All** to install packages and load data (~60 seconds)
3. Work through each cell from top to bottom
4. Pause at `🔧 EXERCISE` cells and try the modifications
5. Ask a facilitator if anything breaks

---

## Presentation Slides

The slide deck is a self-contained HTML file — open it directly in any browser:

```
workshop/presentation/index.html
```

**Keyboard shortcuts:**

| Key | Action |
|-----|--------|
| `→` or `Space` | Next slide |
| `←` | Previous slide |
| `S` | Toggle speaker notes |
| `N` | Toggle slide navigator |
| `P` | Presenter mode |
| `?` | Help overlay |

---

## Optional: Privacy-Preserving LLMs with Ollama

Notebook 3 can run language models entirely on your own machine — no internet required after download, no data leaves your device. This is the approach required for real patient data.

### Install Ollama

**macOS:**
```bash
brew install ollama
ollama pull llama3.2      # ~2 GB download
ollama serve              # Start the local server
```

**Windows:** Download installer from [ollama.ai/download](https://ollama.ai/download)

**Linux:**
```bash
curl -fsSL https://ollama.ai/install.sh | sh
ollama pull llama3.2
```

### Hardware Requirements

| Model | Size | RAM Required | Quality |
|-------|------|-------------|---------|
| llama3.2 | ~2 GB | 8 GB | Good |
| gemma3:4b | ~3 GB | 8 GB | Very good |
| mistral | ~4 GB | 16 GB | Excellent |

Once Ollama is running, set `USE_OLLAMA = True` in the Notebook 3 configuration cell.

**For today's workshop:** `USE_OLLAMA = False` uses the Anthropic API with synthetic data only.

---

## Dataset Information

### Notebooks 1 & 2 — Synthetic ABIDE-Like Dataset

A synthetically generated dataset mirroring the statistical properties of the [ABIDE (Autism Brain Imaging Data Exchange)](http://fcon_1000.projects.nitrc.org/indi/abide/) phenotypic data. **No real patient data is used.**

- n = 500 participants (~50% ASD, ~50% Control)
- Features: AGE_AT_SCAN, SEX, FIQ, VIQ, PIQ, SRS_RAW_TOTAL, ADOS_TOTAL, SCQ_TOTAL, VINELAND_COMMUNICATION_STANDARD_SCORE
- Generated with realistic inter-feature correlations based on published ABIDE statistics
- Random seed 42 — fully reproducible

**Want the real data?** Request access at http://fcon_1000.projects.nitrc.org/indi/abide/

### Notebook 3 — Synthetic Clinical Vignettes

20 entirely fictional youth mental health clinical vignettes (ages 12–24). Programmatically generated to be clinically realistic for demonstration. They do not represent any real individuals or clinical encounters.

### Ethical Use Notice

> These materials are designed for **educational purposes only**. Synthetic datasets are not validated clinical tools and must not be used to make clinical decisions. ML models trained on synthetic data require prospective validation on real clinical populations before any clinical application. Always maintain human oversight in clinical decision-making.

---

## Getting Help During the Workshop

| Problem | Solution |
|---------|----------|
| Colab disconnected | Click "Reconnect" → Runtime → Run All |
| Package not installed | Re-run the first setup cell; wait for "Setup complete ✓" |
| `NameError` on a variable | Runtime → Run All Cells Above |
| SHAP crashes Colab | Reduce to 50 test samples before computing SHAP |
| Ollama not found | Set `USE_OLLAMA = False` in the config cell |
| Anything else | Raise your hand — facilitators are circulating |

---

## Post-Workshop Learning Resources

### Beginner
| Resource | Description |
|----------|-------------|
| [fast.ai Practical ML](https://course.fast.ai) | Best practical ML course for researchers; Python-first, free |
| [Kaggle Learn](https://www.kaggle.com/learn) | Short free courses on pandas, ML, visualization |
| [Elements of AI](https://www.elementsofai.com) | Conceptual introduction, no programming required |
| [scikit-learn tutorials](https://scikit-learn.org/stable/tutorial/) | Excellent examples with tabular data |

### Intermediate
| Resource | Description |
|----------|-------------|
| [Hugging Face NLP Course](https://huggingface.co/learn/nlp-course/) | Transformers and LLMs from first principles |
| [SHAP Documentation](https://shap.readthedocs.io) | Complete guide to explainability |
| [MIT 6.S897 ML for Healthcare](https://mlhc.github.io) | Clinical AI applications; lecture videos and papers |
| [Papers With Code](https://paperswithcode.com) | Open ML papers with code |

### Advanced
| Resource | Description |
|----------|-------------|
| [MLHC Conference Proceedings](https://proceedings.mlr.press) | Leading venue for clinical ML research |
| [Fairlearn](https://fairlearn.org) | Fairness assessment and mitigation for ML |
| [NVIDIA FLARE](https://nvflare.readthedocs.io) | Federated learning framework for healthcare |
| [PhysioNet](https://physionet.org) | Clinical datasets (MIMIC-III/IV) and validated algorithms |

### Open Mental Health Datasets
| Dataset | Description | Access |
|---------|-------------|--------|
| [ABIDE I & II](http://fcon_1000.projects.nitrc.org/indi/abide/) | ASD neuroimaging + phenotypic data | Free registration |
| [DAIC-WOZ](https://dcapswoz.ict.usc.edu) | Depression/anxiety/PTSD clinical interviews | Application required |
| [CLEF eRisk](https://erisk.irlab.org) | Early risk detection from social media text | Annual competition |
| [OpenNeuro](https://openneuro.org) | Community neuroimaging datasets | Open access |
| [PhysioNet MIMIC-IV](https://physionet.org/content/mimiciv/) | Full EHR data from ICU | CITI training required |

### Key Papers Referenced in This Workshop
- Shatte et al. (2019). Machine learning in mental health. *Psychological Medicine*, 49(9), 1426–1448.
- Rajpurkar et al. (2022). AI in health and medicine. *Nature Medicine*, 28, 31–38.
- Obermeyer et al. (2019). Dissecting racial bias in an algorithm used to manage the health of populations. *Science*, 366(6464), 447–453.
- [YOUR CITATION HERE] — ASD prediction
- [YOUR CITATION HERE] — Anomaly detection

---

## Repository Structure

```
PCYMH-Workshop-2026/
├── workshop/
│   ├── presentation/
│   │   └── index.html              # 36-slide HTML/CSS/JS presentation deck
│   ├── notebooks/
│   │   ├── 01_ml_foundations.ipynb         # ML fundamentals (25 min)
│   │   ├── 02_explainability_shap.ipynb    # SHAP explainability (20 min)
│   │   └── 03_privacy_llm_ollama.ipynb     # Privacy-preserving LLMs (20 min)
│   ├── facilitator_guide.md        # Timing, speaker notes, troubleshooting
│   └── README.md                   # This file
├── README.md                       # Repository overview
└── LICENSE                         # MIT License
```

---

## Citation & Acknowledgments

If you adapt or build on these materials, please cite:

```bibtex
@misc{pcymh2026workshop,
  title  = {Practical Introduction to AI for Mental Health Applications: Workshop Materials},
  author = {[YOUR NAME HERE]},
  year   = {2026},
  url    = {https://github.com/[USERNAME]/[REPO]}
}
```

**Acknowledgments:** [FUNDING SOURCE] | [INSTITUTION] | [COLLABORATORS]

**Contact:** [EMAIL ADDRESS] | **GitHub:** [GITHUB_REPO_URL]

---

*Released under the [MIT License](../LICENSE). Free to use, modify, and distribute with attribution.*
