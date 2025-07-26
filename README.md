# 🌟 Traitlytics: Analyzing Personality from LinkedIn Profile Data

> **Predicting Big Five Personality Traits (Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism) from LinkedIn profile text using Machine Learning and Transformer-based models.**

![Traitlytics Header](https://img.shields.io/badge/Big%20Five%20Model-Psychometrics-blue) ![Python](https://img.shields.io/badge/Python-3.9%2B-brightgreen) ![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## 📘 Overview

Personality assessment is vital in behavioral analysis, recruitment, and personal development. Traditional methods—mainly self-reported questionnaires—are prone to bias and lack scalability.

**Traitlytics** introduces a **data-driven, automated framework** for inferring personality from **LinkedIn profiles**. We combine TF-IDF, cosine similarity, and modern deep learning models like **BERT** to predict Big Five personality traits in a professional context.

---

## 🎯 Project Objectives

* Extract and analyze textual data from LinkedIn (summaries, skills, endorsements).
* Use Big Five Personality Dataset (Kaggle) as a reference for label generation.
* Assign trait scores using cosine similarity to profile content.
* Train and compare models:

  * Logistic Regression
  * Support Vector Regressor (SVR)
  * Random Forest Regressor
  * Fine-tuned BERT for regression
* Evaluate performance using RMSE, MAE, R².
* Adhere to privacy and ethical research practices.

---

## 📂 Project Structure

```bash
Traitlytics/
│
├── 📁 code/
│   ├── 📄 DataMining Project.ipynb        # End-to-end modeling pipeline
│   └── 📄 Data transformation.ipynb       # Data cleaning and label assignment
│
├── 📁 data/
│   ├── linkedin_profiles.xlsx               # Scraped LinkedIn data
│   ├── linkedin_with_trait_scores.csv       # Cosine similarity-based labeled data
│   ├── processed_personality_traits.csv     # Cleaned Big Five Personality Dataset
│   └── Sentences.json                       # Big Five definition sentences
│
├── 📄 Report.pdf                            # Detailed project writeup
├── 📄 README.md                             # This file
├── 📄 requirements.txt                      # Python environment setup (to be generated)
└── LICENSE
```

---

## 🔍 Methodology

### 📥 Data Collection

* Public LinkedIn profile data (scraped with Selenium)
* Big Five Personality Dataset (Kaggle, 1M+ rows)

### 🧼 Preprocessing & Annotation

* Text cleaning (punctuation, stopwords)
* Tokenization & lemmatization
* TF-IDF vectorization of LinkedIn text and trait-defining sentences
* Cosine similarity to assign trait scores (1–5) for each user profile

### ⚙️ Model Training

* Treated as a regression task (rather than classification)
* Trained individual models for each trait
* Models used:

  * Logistic Regression (baseline)
  * SVR (Support Vector Regression)
  * Random Forest Regressor (n\_estimators=100)
  * BERT (bert-base-uncased fine-tuned with MSE loss)

### 🧪 Evaluation Metrics

* **RMSE**: Penalizes large errors
* **MAE**: Balanced average error
* **R²**: Proportion of variance explained

| Trait             | Linear Regression | Random Forest | SVR    | BERT       |
| ----------------- | ----------------- | ------------- | ------ | ---------- |
| Extraversion      | 0.6326            | 0.4305        | 0.4147 | **0.4762** |
| Neuroticism       | 0.6410            | 0.4797        | 0.4563 | **0.4844** |
| Agreeableness     | 0.6900            | 0.4776        | 0.4555 | **0.5308** |
| Conscientiousness | 0.5671            | 0.4951        | 0.4610 | **0.5208** |
| Openness          | 0.6190            | 0.5230        | 0.5229 | **0.5557** |

> ⚡ BERT outperforms others across traits due to its superior contextual understanding.

---

## 📚 Sample Prediction

**Profile Summary**:

> “A lifelong seeker of knowledge... exploring frameworks in AI ethics, metaphysics, and creativity.”

**Predicted Personality**:

```
Extraversion:        3.0074
Neuroticism:         2.9990
Agreeableness:       3.0713
Conscientiousness:   3.2820
Openness:            3.7746
```

---

## 💡 Key Learnings

* Cosine similarity is a practical solution for weakly supervised label creation.
* BERT improves psychological text interpretation on formal data.
* TF-IDF remains a robust baseline for professional profile modeling.
* Public profile content can reveal meaningful personality cues.

---

## 🔭 Future Work

* Add multimodal features (images, post engagement)
* Use graph embeddings from connection networks
* Incorporate SHAP/LIME for interpretability
* Expand dataset for more generalizable results
* Explore human-validated labels and survey-based ground truth

---

## ⚙️ Installation & Usage

### ✅ Setup

```bash
git clone https://github.com/yourusername/Traitlytics.git
cd Traitlytics
conda create -n traitlytics_env python=3.9
conda activate traitlytics_env
pip install -r requirements.txt
```

> 🔧 Tip: Generate your `requirements.txt` using:
>
> ```bash
> pip freeze > requirements.txt
> ```

### 📓 Run Notebooks

```bash
jupyter lab  # or jupyter notebook
```

Run in order:

1. `code/Data transformation.ipynb`
2. `code/DataMining Project.ipynb`

---

## 🧾 Required Files

* `linkedin_profiles.xlsx`
* `linkedin_with_trait_scores.csv`
* `processed_personality_traits.csv`
* `Sentences.json`
* `Report.pdf`

---

## 🧑‍💻 Authors

* **Aman Pandey**
* Akshara Balasubramanian
* Jaydeep Patil
* Reuben Roy Kochukudiyil

---

## 📄 License

This project is licensed under the **MIT License** — see the `LICENSE` file.

---

## 🌐 Contributions

All contributions are welcome — fork, improve, and submit a pull request!

> *This README merges clean GitHub formatting with rich technical content and detailed project flow from academic research. Perfect for both collaborators and recruiters.*
