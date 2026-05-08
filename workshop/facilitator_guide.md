# Facilitator Guide: Practical Introduction to AI for Mental Health Applications
## 75-Minute Interactive Workshop

**Version:** 1.0 | **Conference:** PCYMH 2026 | **Updated:** [DATE]

---

## Table of Contents
1. [Pre-Workshop Checklist](#1-pre-workshop-checklist)
2. [Minute-by-Minute Run Sheet](#2-minute-by-minute-run-sheet)
3. [Common Questions & Suggested Answers](#3-common-questions--suggested-answers)
4. [Troubleshooting Guide](#4-troubleshooting-guide)
5. [Ollama Installation Instructions](#5-ollama-installation-instructions)
6. [Slide-by-Slide Speaker Notes](#6-slide-by-slide-speaker-notes)
7. [Dataset Substitution Guide](#7-dataset-substitution-guide)

---

## 1. Pre-Workshop Checklist

### One Week Before
- [ ] Confirm room booking has projector, audio, and sufficient power outlets for laptops
- [ ] Test all 3 notebooks end-to-end in Google Colab (fresh session, Runtime → Run All)
- [ ] Confirm Colab notebook URLs are publicly accessible (File → Share → Anyone with link)
- [ ] Create shortened URLs (bit.ly or tinyurl) for each notebook
- [ ] Create QR codes for each notebook URL
- [ ] Print 1-page quick-start guide (QR codes + WiFi info) if desired
- [ ] Test `presentation/index.html` in Chrome, Firefox, Safari — confirm all 36 slides load
- [ ] Test keyboard shortcuts: ArrowRight, S (notes), N (sidebar), ? (help)
- [ ] Confirm you have an Anthropic API key for the Notebook 3 demo
- [ ] If planning Ollama live demo: pre-download `llama3.2` on demo laptop (`ollama pull llama3.2`)
- [ ] Review slide-by-slide speaker notes (Section 6 of this guide)
- [ ] Export a PDF backup of the slides in case of projector/browser issues

### One Day Before
- [ ] Load all 3 notebooks in Colab tabs and pre-run setup cells (caches the pip installs)
- [ ] Set `ANTHROPIC_API_KEY` in Colab Secrets for Notebook 3
- [ ] Test WiFi speed at venue if possible — if slow, pre-install packages before workshop
- [ ] Confirm co-facilitator roles: who circulates during hands-on, who monitors questions
- [ ] Talk through the Common Questions section with co-facilitators
- [ ] Charge all devices
- [ ] Download offline backup: `jupyter nbconvert --to html` for each notebook

### Day Of
- [ ] Arrive 30 minutes early
- [ ] Open presentation on projector, confirm slide 1 displays correctly
- [ ] Open all 3 Colab notebooks in browser tabs, verify they load
- [ ] Write WiFi credentials and short notebook URLs on whiteboard or slide
- [ ] Have co-facilitator(s) ready to circulate during hands-on segments
- [ ] Place QR code printouts on tables if prepared
- [ ] Confirm timing: start on the dot, end by T+75 min

---

## 2. Minute-by-Minute Run Sheet

### 00:00–02:00 — Welcome & Housekeeping (Slides 1–2)

**Facilitator action:** Begin promptly. Advance to slide 1.

**Talking points:**
- "Welcome everyone. This is a hands-on session — roughly half slides, half Python notebooks. No coding experience is required."
- Point to QR code / URL: "If you haven't already, scan this now and open Notebook 1 in Colab."
- Announce WiFi credentials. Mention bathroom location.
- "We move at a brisk pace. If you get lost, your neighbour is your best resource, and facilitators will circulate."

---

### 02:00–05:00 — Presenter Introductions + Learning Objectives (Slides 3–4)

**Facilitator action:** Brief self-introduction and co-facilitator introductions (~60 seconds total). Then advance to slide 4.

**Talking points (Slide 4):**
- Click once: "Objective 1 — understanding the concepts."
- Click again: "Objective 2 — hands-on skills."
- "If you leave today able to explain what a machine learning model does and why SHAP matters for clinical AI, we've succeeded."

---

### 05:00–12:00 — Section 1: The AI Landscape (Slides 5–9)

**Target pace:** ~84 seconds per slide.

**Slide 5 — Why AI, Why Now?**
- Point to each timeline milestone. "This is the arc from academic curiosity to clinical tool."
- Key message: "The convergence of data, compute, and algorithms happened in the last decade. This is why we're having this conversation now."

**Slide 6 — Vocabulary**
- "When a vendor says 'AI-powered' — ask them: what kind of AI? Rule-based system from 1985 or a transformer model from 2023?"
- "LLMs like ChatGPT are a tiny subset of AI. But they've gotten outsized attention."

**Slide 7 — Healthcare Applications**
- "We're focusing on Early Detection and Risk Stratification — the areas with the most mature clinical AI literature, and most relevant to this audience."

**Slide 8 — Mental Health AI**
- Walk through each example briefly. Read the warning box aloud.
- "ASD screening from behavioral assessments is exactly what Notebook 1 demonstrates."

**Slide 9 — LLMs**
- "The 'open-weight' distinction is critical for clinical use — that's what Notebook 3 explores."

---

### 12:00–24:00 — Section 2: ML Fundamentals + Notebook 1 Live Demo (Slides 10–16)

**Slide 10** (20 sec): Announce section.

**Slide 11 — The ML Paradigm** (90 sec):
- "Traditional programming: human writes the rules. ML: the algorithm discovers the rules from examples."
- "The algorithm doesn't understand the data — it finds patterns. Powerful and risky."

**Slide 12 — Types of ML** (90 sec):
- Focus on supervised learning. "That's what Notebook 1 uses."

**Slide 13 — The Pipeline** (2 min):
- Use click-to-reveal animation. One step per click.
- At each step: "Where could this go wrong? Where does clinical expertise matter?"
- At Deployment: "Most academic research stops at Evaluation. Deployment is where the real work begins."

**Slide 14 — Key Concepts** (90 sec):
- "Overfitting is a model that memorized the training set. It aces the practice exam but fails the real test."

**Slide 15 — Evaluation Metrics** (90 sec):
- "Memorize the four confusion matrix quadrants — everything else follows."
- Read the accuracy warning slowly, with emphasis.

**Slide 16 — Notebook 1 Callout** (1 min):
- Switch to browser. Open Colab Notebook 1. Run the setup cell.
- "While this installs (about 60 seconds), read the markdown explaining what each line does."

---

### 24:00–37:00 — Notebook 1 Hands-On (13 minutes)

**Facilitator action:** Both facilitators circulate the room.

**Pacing prompts to project or announce:**
- T+5 min: "Everyone should be past Section 2 — the EDA plots."
- T+10 min: "Move to Section 4 — Logistic Regression — if you haven't already."
- At the confusion matrix cell: ask a volunteer to read their accuracy aloud. Follow up: "Is that good enough for a clinical screening tool?"

**Common issues to look for:**
- `ModuleNotFoundError: No module named 'shap'` → re-run the pip install cell
- `NameError` → skipped a cell; Runtime → Run All Cells Above
- Colab disconnect → Reconnect → Runtime → Run All

**At 13 minutes:** "Let's come back together. Who found a result that surprised them?"

---

### 37:00–47:00 — Section 3: Explainability + Notebook 2 Demo (Slides 17–22)

**Slide 17** (15 sec): Announce section.

**Slide 18 — Black Box Problem** (90 sec):
- "A clinician who doesn't understand why a model made a recommendation cannot be held accountable for acting on it — and shouldn't be."
- "FDA's 2021 AI/ML Action Plan explicitly requires transparency documentation for clinical decision support tools."

**Slide 19 — Explainability Methods** (60 sec):
- "Global: how does the model work in general. Local: why did it make THIS recommendation for THIS patient."
- "In a clinical workflow, local explanations are what matter."

**Slide 20 — SHAP in Plain English** (90 sec):
- Walk through the bar chart. "Positive SHAP value = pushes toward ASD. Negative = pushes toward Control."

**Slide 21 — Bias & Fairness** (90 sec):
- Read the specific risks aloud. Reference Obermeyer et al.: "A commercially deployed algorithm used by hundreds of hospitals showed systematic racial bias. Not malice — encoded historical inequity."

**Slide 22 — Notebook 2 Callout** (30 sec):
- Quick live demo: open Notebook 2, run the SHAP beeswarm cell, show output.

---

### 47:00–55:00 — Notebook 2 Hands-On (8 minutes)

**Key exercise to highlight:** Finding a wrong prediction and using SHAP to diagnose why.
- "Find a patient where the model predicts incorrectly. Look at their waterfall plot. Which features misled it?"

---

### 55:00–65:00 — Section 4: Privacy AI + Notebook 3 Demo (Slides 23–28)

**Slide 24 — Why Privacy Matters** (2 min):
- "This is the slide to screenshot. If someone in your department is using ChatGPT with patient information, they are likely violating institutional policy and provincial law."

**Slide 25 — Ollama** (90 sec):
- If using Ollama live: switch to terminal, run `ollama run llama3.2`.
- "This model runs entirely on my laptop. No network traffic. No API key. No data leaves this room."

**Slides 26–27** (90 sec each): Walk through use cases and federated learning concept.

**Slide 28 + Notebook 3 demo** (1 min):
- Open Notebook 3. Run the vignette generation cell. Show the synthetic dataset.

---

### 65:00–70:00 — Section 5: Clinical Integration (Slides 29–33)

**Move through 5 slides in ~5 minutes.**

- Slide 30: "The implementation gap is real. Publish the model, then spend 3–5 years getting it into clinical use. Plan for this from the start."
- Slide 31: "These five action items are your homework. Which one is your immediate next step?"
- Slide 33: "This ethical framework is increasingly required explicitly in grant applications and ethics submissions."

---

### 70:00–75:00 — Q&A and Wrap-Up (Slides 34–36)

- Show slide 34. "What's one thing you'll try in the next month?" Take 2–3 responses.
- Open Q&A. Reference pre-prepared answers in Section 3.
- Slide 35 (Resources): "All of these are on the GitHub repo."
- Slide 36: Thank the audience. Mention GitHub repo. Photo opportunity with QR code slide.

---

## 3. Common Questions & Suggested Answers

**Q1: "Isn't AI going to replace clinicians?"**
> No — and the evidence is consistent on this. AI performs best as augmentation: it processes data faster and at greater scale than any human, but lacks contextual understanding, therapeutic relationship, and ethical judgment. The better framing is that AI changes *what* clinicians do, not *whether* they're needed. The most effective clinical AI systems keep humans firmly in the loop for consequential decisions.

**Q2: "What data do I need to get started?"**
> You need labeled examples — data points where you know the outcome. For depression prediction: patient features (assessments, demographics, clinical notes) paired with outcomes (diagnosis, relapse, treatment response). A minimum of 200–500 labeled examples works for simple models; complex models need thousands. Start with data you already collect routinely — you'd be surprised what's in your EHR or research database.

**Q3: "How accurate do models need to be to be clinically useful?"**
> It depends entirely on the clinical task. For a population-level screening tool, 70% sensitivity at 80% specificity might be useful if it beats the status quo (no screening). For a diagnostic aid where a false positive leads to a biopsy, you might need 95%+ specificity. Accuracy as a single number is almost never the right metric — specify the clinical use case first, then determine acceptable performance thresholds.

**Q4: "Can I use ChatGPT or Claude.ai for my research?"**
> For non-sensitive tasks (literature review, writing assistance, code generation) — yes, with verification. For anything involving patient data — only if using synthetic data, or fully de-identified data AND your institutional data governance policy permits it. Most policies prohibit sending identifiable health information to external cloud APIs. When in doubt, use Ollama locally or consult your institution's privacy officer.

**Q5: "How do I get REB/IRB approval for an ML study?"**
> ML studies using existing clinical data typically fall under retrospective chart review or secondary data analysis. Key elements for your ethics application: data source description, de-identification procedures, model validation approach, privacy safeguards, and plan for communicating uncertainty. Many REBs are still developing frameworks for clinical AI — be prepared to educate reviewers. Reference Health Canada's guidance on AI/ML in health and your institution's data governance policy.

**Q6: "What's the difference between SHAP and LIME?"**
> Both are local explainability methods. LIME approximates the model locally with a simpler interpretable model. SHAP is theoretically grounded in cooperative game theory (Shapley values) and satisfies consistency and local accuracy properties that LIME doesn't guarantee. For tree-based models (Random Forest, XGBoost), SHAP's TreeExplainer is exact and fast — making it the preferred choice in most clinical AI contexts.

**Q7: "Is federated learning actually used in practice?"**
> Yes, increasingly. NVIDIA FLARE is deployed across several academic medical centers for federated survival analysis and imaging studies. The EU's HealthChain project used it for multi-site cancer research. It's not plug-and-play — it requires significant technical infrastructure — but tools are maturing rapidly.

**Q8: "What about the environmental cost of large AI models?"**
> A fair concern. Training large foundation models (GPT-4, Llama) requires enormous compute and energy. However, clinical research typically uses: (1) pre-trained open-weight models fine-tuned on small datasets, or (2) traditional ML models like Random Forest that train in minutes on a laptop. The energy cost is minimal compared to foundation model pre-training.

**Q9: "How do I evaluate whether my model is fair across demographic groups?"**
> At minimum: stratify your performance metrics (AUC, F1, precision, recall) by key demographic groups (sex, age category, race/ethnicity if captured, SES proxy). Use tools like Fairlearn (Microsoft) or AI Fairness 360 (IBM) for formal auditing. The Notebook 2 SHAP fairness analysis is a starting point. Also audit your data for systematic missingness by group before training.

**Q10: "Can I use these notebooks with my own institutional data?"**
> Absolutely — that's the intent. Main changes: (1) replace the synthetic dataset generation with your data loading code, (2) update `feature_cols` to match your variable names, (3) update the target variable, (4) adjust preprocessing for your data's characteristics. The ML pipeline, SHAP analysis, and LLM integration all transfer directly. Contact us via the GitHub repo if you'd like guidance.

**Q11: "What about multimodal data — combining imaging, EHR, and genomics?"**
> Multimodal AI is an active research frontier. Current approaches include early fusion (concatenate features from each modality), late fusion (train separate models, combine predictions), and attention-based cross-modal architectures. The ABIDE dataset actually includes both neuroimaging and phenotypic data — a real multimodal example. Main challenges are data availability and increased complexity in validation.

**Q12: "What's the best way to keep learning after today?"**
> Three paths depending on background: (1) No programming experience → fast.ai's Practical Deep Learning course (Python-first, top-down). (2) Statistical background → Elements of Statistical Learning (free PDF) + scikit-learn documentation. (3) Clinical AI focus → Machine Learning for Healthcare (MIT OpenCourseWare) + MLHC conference proceedings. All are freely available online.

---

## 4. Troubleshooting Guide

### Google Colab Issues

**"Runtime disconnected" or "Session expired"**
- Click "Reconnect" then Runtime → Run All. If pip install already ran, it will re-run (~60 sec).

**"ModuleNotFoundError: No module named 'shap'"**
- The pip install cell didn't complete. Scroll to top, re-run the setup cell. Wait for "Setup complete ✓".

**"NameError: name 'X_train_scaled' is not defined"**
- Cells were run out of order. Runtime → Run All Cells Above from the current cell.

**Kernel dies during SHAP computation**
- Insufficient RAM on free Colab. Before the TreeExplainer cell, add:
  `X_test_shap = X_test_s.sample(50, random_state=42)` and use `X_test_shap` instead of `X_test_s`.

**Slow package installation (>3 minutes)**
- Warn attendees to run the setup cell immediately when they open the notebook. It can take 3–5 minutes on slow WiFi.

**"403 Forbidden" when opening Colab link**
- Notebook isn't shared publicly. In Google Drive: right-click → Share → Anyone with link → Viewer. Re-share the link.

**"This notebook requires GPU"**
- All workshop notebooks run on CPU. If this message appears, click "Run Anyway."

### Anthropic API Issues (Notebook 3)

**"AuthenticationError: invalid_api_key"**
- In Colab: left sidebar → Key icon → Add secret: Name = `ANTHROPIC_API_KEY`, Value = `sk-ant-...`
- Alternatively, in the notebook config cell: `import os; os.environ["ANTHROPIC_API_KEY"] = "your-key"`

**"RateLimitError"**
- Add `time.sleep(1)` between API calls, or reduce the number of vignettes processed in the demo.

**API responses slow (>5 seconds)**
- `claude-haiku-4-5-20251001` is the fastest available model. Set `max_tokens=150` for shorter responses.

### Ollama Issues

**"ollama: command not found"**
- Ollama isn't installed. Follow Section 5. For the workshop, switch to `USE_OLLAMA = False`.

**Model responses very slow (>30 sec)**
- Laptop doesn't have enough RAM or is swapping. For 3B models, 8 GB RAM is the minimum. Switch to cloud mode.

**"Error: model not found"**
- Model hasn't been downloaded. Run `ollama pull llama3.2` in a terminal first.

---

## 5. Ollama Installation Instructions

### macOS

```bash
# Option 1: Homebrew (recommended)
brew install ollama
ollama serve              # Start the server
ollama pull llama3.2     # Download model (~2.0 GB)
ollama pull gemma3:4b    # Alternative: Google's model (~3.3 GB)
ollama run llama3.2      # Interactive test
```

Alternatively: download the macOS app from https://ollama.ai/download

### Windows

1. Download installer from https://ollama.ai/download/windows
2. Run `OllamaSetup.exe` — Ollama starts in the system tray automatically
3. Open PowerShell or Command Prompt:
```powershell
ollama pull llama3.2
ollama run llama3.2
```

### Linux

```bash
curl -fsSL https://ollama.ai/install.sh | sh
systemctl start ollama    # Starts as a systemd service
ollama pull llama3.2
ollama run llama3.2
```

### Hardware Requirements

| Model | Parameters | Download | RAM Min | GPU VRAM (optional) |
|-------|-----------|----------|---------|---------------------|
| llama3.2 | 3B | ~2.0 GB | 8 GB | 4 GB |
| gemma3:4b | 4B | ~3.3 GB | 8 GB | 4 GB |
| mistral | 7B | ~4.1 GB | 16 GB | 8 GB |
| llama3.1:8b | 8B | ~4.7 GB | 16 GB | 8 GB |

Models run on CPU without GPU — slower but functional. Apple Silicon (MPS), NVIDIA, and AMD ROCm GPUs all accelerate inference significantly.

### Using Ollama in Python

```python
import requests

response = requests.post(
    "http://localhost:11434/api/generate",
    json={"model": "llama3.2", "prompt": "Your prompt here", "stream": False},
    timeout=60
)
print(response.json()["response"])
```

---

## 6. Slide-by-Slide Speaker Notes

**Slide 1 (Title):** Welcome attendees warmly. This is a practical session — half slides, half code. No coding experience needed. All materials are freely available via the QR code. Point to it explicitly.

**Slide 2 (Housekeeping):** Confirm WiFi credentials are visible. Mention bathroom location. Emphasize 75-minute format: "We'll move briskly — the goal is exposure and hands-on experience, not mastery today."

**Slide 3 (Presenters):** Keep introductions to 30–45 seconds each. Mention your clinical or research context to establish credibility.

**Slide 4 (Learning Objectives):** Click once per objective. "Most workshops about AI in health don't have you running code. We do."

**Slide 5 (Why AI Now):** The timeline animation is a conversation starter. "Who remembers the hype around expert systems in the 1980s?" This contextualizes current AI excitement in a longer history of cycles.

**Slide 6 (Vocabulary):** The nested circles often generate questions. Be direct: "An LLM is a type of deep learning model, which is a type of ML, which is a type of AI." Helps cut through marketing language.

**Slide 7 (Healthcare Applications):** Make explicit: "Everything we do today serves these two applications — early detection and risk stratification — in youth mental health."

**Slide 8 (Mental Health AI):** Read the warning box aloud. "Every application on this slide has peer-reviewed evidence behind it. And every application requires extensive validation before deployment. Both things are true."

**Slide 9 (LLMs):** "Llama 3 from Meta runs on your laptop. GPT-4 from OpenAI does not. That difference matters enormously for clinical use with real patient data."

**Slide 10 (ML Section Header):** Brief pause. "This section is conceptually dense — the notebook will make it concrete."

**Slide 11 (ML Paradigm):** Most important conceptual slide. "Traditional programming is like writing a recipe. ML is like watching a chef cook 10,000 meals and inferring the recipe from observations."

**Slide 12 (Types of ML):** Quick pace. "Unsupervised learning is powerful for phenotyping — identifying subgroups of patients sharing biological or clinical characteristics."

**Slide 13 (Pipeline):** Use click-reveal deliberately. At each step: "What can go wrong here?" Preprocessing: data quality. Feature engineering: domain knowledge gaps. Evaluation: wrong metrics.

**Slide 14 (Key Concepts):** "The bias-variance curve: overfitting is a model that aced the exam it studied but fails the real test."

**Slide 15 (Evaluation):** Read the warning box slowly. "A model that always says 'no depression' would be 95% accurate in a general population — and completely useless clinically."

**Slide 16 (Notebook 1):** Transition energy. "Let's build one. Open your laptops." Switch to browser, run the setup cell live.

**Slide 17 (Explainability Header):** "This section matters most for clinical adoption. Without explainability, models remain toys."

**Slide 18 (Black Box):** Let the animation play. "Clinicians make decisions they can defend. A black box gives them nothing to defend."

**Slide 19 (Explainability Methods):** "Global says what the model generally cares about. Local says why it cared about this specific patient."

**Slide 20 (SHAP):** Walk through the bar chart. "Positive SHAP = pushes toward ASD. Negative = pushes toward Control. The magnitude is the strength of that push."

**Slide 21 (Bias & Fairness):** This generates strong reactions. Be prepared for extended discussion. The Obermeyer paper is a powerful reference — many in the room will have heard of it.

**Slide 22 (Notebook 2):** Quick demo of the beeswarm plot if time permits.

**Slide 23 (Privacy Header):** "For many of you, this is the most immediately practical section. You have data. You have questions. You can't send the data to OpenAI. What do you do?"

**Slide 24 (Privacy Matters):** "The cloud API column describes what happens every time you paste clinical information into ChatGPT.com. The local model column describes what Ollama gives you."

**Slide 25 (Ollama):** If you have Ollama running, switch to terminal for a live demo. Watching a clinical task run locally, with no internet, is often the 'aha' moment of the workshop.

**Slide 26 (Use Cases):** "Pick the one most relevant to your work. For many: de-identification or structured extraction — bottlenecks in your current research workflow."

**Slide 27 (Federated Learning):** Conceptual only. "You don't need to implement this today. But know it exists when designing multi-site studies."

**Slide 28 (Notebook 3):** "This is the capstone — connecting LLMs for text processing to the ML pipeline from Notebook 1."

**Slide 29 (Clinical Integration Header):** "We've built the models. Now the hard part: getting them to patients."

**Slide 30 (Implementation Gap):** "Fewer than 1% of published clinical AI models have been prospectively validated. Of those, fewer still have been deployed in practice. The field has a translation problem."

**Slide 31 (Your Roadmap):** "These five steps are concrete and actionable. Write down which one is your immediate next step."

**Slide 32 (Emerging Frontiers):** "Where I'd place my research bets for the next 5 years."

**Slide 33 (Ethical Framework):** "Print this slide. Put it in your grant applications. Funding bodies increasingly require this kind of framework explicitly."

**Slide 34 (Takeaways):** Pause on each bullet. "Which one surprised you most?"

**Slide 35 (Resources):** "All free. The fast.ai course is exceptional for researchers with statistical backgrounds."

**Slide 36 (Thank You):** Thank warmly. Mention GitHub repo URL. Invite follow-up questions via email. "If you adapt these notebooks, let us know what you build."

---

## 7. Dataset Substitution Guide

### Replacing the Synthetic ABIDE Data (Notebooks 1 & 2)

The synthetic dataset is generated by `generate_abide_dataset()` in Notebook 1. To use your own data:

**Step 1: Load your data**
```python
# Replace the generate_abide_dataset() call with:
df = pd.read_csv('your_data.csv')
# or
df = pd.read_excel('your_data.xlsx')
```

**Step 2: Align column names**
```python
df = df.rename(columns={
    'patient_age': 'AGE_AT_SCAN',
    'sex_coded': 'SEX',
    'srs_total': 'SRS_RAW_TOTAL',
    'outcome': 'DX_GROUP'
})
```

**Step 3: Update feature_cols**
```python
feature_cols = ['AGE_AT_SCAN', 'SEX', 'YOUR_FEATURE_1', 'YOUR_FEATURE_2', ...]
```

**Step 4: Ensure binary target**
```python
# If your outcome is 'Yes'/'No':
df['DX_GROUP'] = (df['DX_GROUP'] == 'Yes').astype(int)
```

**Step 5: Check class balance**
```python
print(df['DX_GROUP'].value_counts())
# If severely imbalanced, add class_weight='balanced' to sklearn model constructors
```

### Replacing the Synthetic Vignettes (Notebook 3)

Replace the `VIGNETTES_RAW` list with vignettes from your own context:
- For de-identification demos: add real-looking (but fictional) PHI to the vignette text
- For extraction demos: use notes that contain the fields you want to extract
- Keep vignettes to ~80–150 words for reliable LLM processing

### Ethical Considerations When Using Real Data

- Confirm REB/IRB approval covers ML secondary analysis
- Verify data governance approval for the storage location (Colab, institutional HPC)
- If using identifiable data, use Ollama (local mode) for Notebook 3 — **NOT** the Anthropic API
- Document preprocessing decisions (what was imputed, excluded) for reproducibility
- Conduct a pre-analysis plan when possible to reduce risk of post-hoc hypothesis generation
- Stratify all performance metrics by key demographic groups before reporting results
