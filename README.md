# 🥈 2nd Place Solution - Ghana's Indigenous Intel Challenge

**Author:** Mohamed Amin Kharrat  
**Competition:** [Zindi - Ghana's Indigenous Intel Challenge]https://zindi.africa/competitions/ghana-indigenous-intel-challenge  
**Final Rank:** 2nd / 500+ participants  
**Private Score:** 0.97 

---

## 📊 Overview

This repository contains the complete solution that achieved **2nd place** in Zindi's Ghana Indigenous Weather Forecasting Challenge. The approach combines traditional indigenous ecological knowledge with modern machine learning through an advanced ensemble system.

### Key Achievements
- ✅ Full SHAP explainability analysis
- ✅ Leak-safe cross-validation strategy
- ✅ Domain-specific feature engineering (Ghana seasonal patterns)

---

## 🚀 Quick Start

### Requirements
```bash
pip install -r requirements.txt
```

### Run the Solution
```bash
# Option 1: Run the complete notebook
jupyter notebook notebook.ipynb

# Option 2: Run modular scripts
python src/preprocessing.py
python src/feature_engineering.py
python src/models.py
```

---

## 🧠 Solution Approach

### 1. **Data Preprocessing**
- Deterministic byte-stable cleaning pipeline
- Missing value flagging (3 binary features)
- Text normalization and imputation

### 2. **Feature Engineering** (The Core Differentiator)
- **Cyclical temporal encoding** (sin/cos for hour, month, day)
- **Ghana-specific seasonal features** (bimodal rainy seasons)
- **TF-IDF on indigenous descriptions** (50 features, bigrams)
- **Confidence interactions** (polynomial + cross-features)
- **Leak-safe aggregations** (user/community/district stats)

### 3. **Model Ensemble**
- **LightGBM** (35%) - Fast, leaf-wise growth
- **XGBoost** (35%) - Strong regularization
- **CatBoost** (30%) - Categorical handling
- **Meta-learner:** Logistic Regression on stacked OOF predictions

### 4. **Validation Strategy**
- Stratified 10-fold CV
- Leak-safe per-fold aggregation recalculation
- Early stopping (200 rounds patience)
- Balanced class weighting

---

## 📈 Results

| Metric | Score |
|--------|-------|
| Base Models Avg F1 | 0.9686 ± 0.013 |
| Stacking Meta F1 | 0.697 |
| Improvement over Baseline | +12.7% |

### Top 5 Most Important Features (SHAP)
1. `user_confidence_std` (0.16) - Farmer consistency
2. `user_id` (0.12) - Individual expertise
3. `comm_target_mode` (0.11) - Community baseline
4. `day_of_year` (0.10) - Long-term seasonality
5. `comm_conf_mean` (0.09) - Community confidence

---

## 📄 Documentation

**Full technical write-up:** [solution_writeup.pdf](solution_writeup.pdf)

Includes:
- Detailed feature engineering rationale
- SHAP explainability analysis
- Model architecture justification
- Reproducibility guidelines

---

## 🛠️ Tech Stack

- **Python 3.8+**
- **LightGBM, XGBoost, CatBoost**
- **scikit-learn** (preprocessing, meta-learner)
- **SHAP** (explainability)
- **Pandas, NumPy** (data manipulation)
- **TF-IDF** (text features)

---

## 💡 Key Innovations

1. **Cyclical Time Encoding** - Captures periodicity (11pm ≈ 1am)
2. **Ghana Seasonal Features** - Domain knowledge (Apr-Jun, Sep-Nov rainy periods)
3. **Leak-Safe Aggregations** - Per-fold recalculation prevents CV inflation
4. **Stacking with Logistic Regression** - Learns base model trustworthiness

---

## 📧 Contact

**Mohamed Amin Kharrat**  
- LinkedIn: [linkedin.com/in/med-amin-kharrat-7105a131a](https://www.linkedin.com/in/med-amin-kharrat-7105a131a/)
- GitHub: [github.com/amin03941](https://github.com/amin03941)
- Zindi: [@medamin_kharrat](https://zindi.africa/users/medamin_kharrat)

---

## 📜 License

MIT License - 

---

## 🙏 Acknowledgments

- **Zindi Africa** for hosting the competition
- **RAIL** for sponsoring and providing the challenge


---

**⭐ If you find this solution helpful, please star the repo!**