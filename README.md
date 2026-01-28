# 🎮 Game Rating Prediction Using Pre- and Post-Release Features

A two-stage **machine learning framework** to predict **video game critic and user ratings** by modeling the game lifecycle — **before release (expectations)** and **after release (player experience)**.

This project is designed as a **research-oriented study** and is accompanied by a conference-style paper.

---

## 🚀 Project Overview

Video game reception changes over time:

- **Before release** → ratings are driven by expectations, studio reputation, pricing, and perceived scope  
- **After release** → ratings are driven by gameplay quality, replayability, and execution

To capture this distinction, this project implements **two separate models**:

### 🟦 Model 1: Pre-Release Prediction  
Predicts expected ratings using only features available **before launch**.

### 🟩 Model 2: Post-Release Prediction  
Predicts realized ratings using **execution-level in-game features**.

Critic ratings and user ratings are modeled **independently** in both stages.

---

## 📊 Dataset

The dataset was **manually curated** and engineered from publicly available sources.

### 🔗 Data Sources
- IGDB  
- HowLongToBeat  
- IGN  
- Steam  
- Metacritic  
- IMDb  

### 🗂 Dataset Versions
- **Pre-release dataset:** 170 games (final version used for Model 1 results)
- **Post-release dataset:** Expanded dataset used for Model 2

The dataset emphasizes **interpretability, temporal validity, and feature relevance** rather than scale alone.

---

## 🛠 Feature Engineering

### 🔹 Pre-Release Features
- Genre, platforms, modes (counts + binary indicators)
- Launch price and playtime-based value metrics
- Open-world, sequel/spinoff, modding support
- Studio and franchise historical average ratings
- Unique factor indicator for non-generic experiences

### 🔹 Post-Release Features
- Story depth
- Gameplay quality
- Replayability
- World immersion
- Narrative and audio quality indicators

Derived features such as **price per story hour** and **content density** were used to capture perceived value.

---

## 🤖 Models Used

- 🌳 Random Forest Regressor (primary model)
- 📈 Gradient Boosting Regressor
- ⚡ XGBoost Regressor

Random Forest was selected as the primary model due to its **robust performance and interpretability**.

---

## 📐 Evaluation Metrics

Models were evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

All evaluations were performed **separately for critics and users**.

---

## 🧠 Key Findings

- Pre-release prediction shows **moderate predictability**, driven mainly by:
  - Studio reputation
  - Pricing
  - Modding support
- Post-release prediction achieves **significantly higher accuracy**, dominated by:
  - Replayability
  - Gameplay quality
  - Narrative depth
- Critic ratings are more predictable than user ratings
- Replayability is the strongest post-release predictor across models

---

## 📁 Repository Structure

game-rating-prediction/
│
├── data/
│   ├── Games List 170.csv
│   ├── In Game Features.csv
│   └── games_engineered.md
│
├── notebooks/
│   ├── game_rating_prediction_pre_release.ipynb
│   ├── game_rating_prediction_post_release.ipynb
│
├── results/
│   └── metrics_summary.txt
│
├── README.md
└── requirements.txt



---

## 📄 Research Paper

A **conference-style research paper** based on this project is currently **in preparation**, covering:
- Dataset construction
- Feature engineering
- Model comparison
- Results, discussion, and future work

---

## ⚠ Notes

- This repository is intended as a **research artifact**
- Focus is on **interpretability and lifecycle-aware modeling**
- Large language models were used only for **limited assistance in feature standardization**, with all outputs manually reviewed

---

## 👤 Author

**Paritosh Vishwasrao**

🎓 Aspiring MS in Data Science / AI  
📊 Interests: Applied ML, Game Analytics, Predictive Modeling

---


