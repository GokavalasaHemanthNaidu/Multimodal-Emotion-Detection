<div align="center">

<img src="https://img.shields.io/badge/Emotion%20Detection-Multimodal%20AI%20System-8A2BE2?style=for-the-badge&logo=heart&logoColor=white" alt="Emotion Detection"/>

# 🧠 Multimodal Emotion Detection

### *A robust AI system integrating physiological, audio, and text data*

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)]()
[![XGBoost](https://img.shields.io/badge/XGBoost-Gradient%20Boosting-000000?style=flat-square&logo=xgboost&logoColor=white)]()
[![Signal Processing](https://img.shields.io/badge/Signal%20Processing-Librosa-8A2BE2?style=flat-square)]()
[![Status: Prototype](https://img.shields.io/badge/Status-Completed-9400D3)]()

**[🐛 Report Bug](https://github.com/GokavalasaHemanthNaidu/Multimodal-Emotion-Detection/issues)**

</div>

---

## 🌟 What is Multimodal Emotion Detection?

Human emotion is highly complex and rarely expressed through a single medium. A person might smile (visual) while speaking angrily (audio) and experiencing high stress (heart rate). 

This project is a **Multimodal AI System** designed to predict emotional states by fusing three distinct data streams:
1. **Text** (Linguistic analysis)
2. **Audio** (Vocal tone and pitch)
3. **Physiological Signals** (Heart Rate / ECG)

By utilizing a **Late Fusion Strategy**, the system combines the independent probabilities from these distinct models into a final, highly accurate emotional classification.

---

## ✨ Key Features & Performance

| Feature | Details | Performance Metrics |
|---|---|---|
| 🫀 **Physiological Data** | Real-time heart rate variation analysis | Handled class imbalance natively |
| 🎙️ **Audio Processing** | MFCC feature extraction via Librosa | Fused directly into the meta-classifier |
| 📝 **Text Classification** | NLP vectorization and sentiment extraction | **0.93 Weighted F1-Score** |
| 🧠 **Model Ensembling** | SVM, LightGBM, Random Forest, XGBoost | **92.8% Overall Accuracy** |

---

## 🏗️ Architecture: The Late Fusion Strategy

Rather than concatenating the raw data (Early Fusion), this system utilizes a **Late Fusion (Stacking)** architecture to prevent dimensionality issues and allow specialized models to handle their respective data types.

```text
[ Raw Audio ] ──────▶ [ MFCC Extractor ] ────▶ [ Audio SVM ] ────────┐
                                                                     │
[ Raw Text ] ───────▶ [ TF-IDF Vectorizer ] ─▶ [ Text XGBoost ] ─────┼──▶ [ Meta-Classifier (LightGBM) ] ──▶ Final Emotion
                                                                     │
[ Heart Rate ] ─────▶ [ Time-Series Feat. ] ─▶ [ Physio RF ] ────────┘
```

**Why Late Fusion?**
- Prevents text embeddings from mathematically dominating the smaller heart rate features.
- Allows each modality to be trained on the algorithm best suited for its domain.

---

## 💻 Tech Stack

* **Language:** Python 3.11+
* **Machine Learning:** Scikit-Learn, XGBoost, LightGBM
* **Audio Processing:** Librosa
* **Text Processing:** NLTK, TF-IDF
* **Data Manipulation:** Pandas, NumPy

---

## 🚀 Future Roadmap

- [ ] Transition from traditional ML to Deep Learning (Transformers for text, CNNs for audio spectrograms).
- [ ] Implement Early Fusion attention mechanisms to compare against the current Late Fusion approach.
- [ ] Build a real-time inference FastAPI backend.

---

## 👨‍💻 Author
**Gokavalasa Hemanth Naidu**
- GitHub: [@GokavalasaHemanthNaidu](https://github.com/GokavalasaHemanthNaidu)
- LinkedIn: [in/gokavalasahemanthnaidu](https://www.linkedin.com/in/gokavalasahemanthnaidu/)