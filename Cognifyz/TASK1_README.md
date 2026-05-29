# Task 1 — Predict Restaurant Ratings 🤖⭐

**Cognifyz Technologies — Machine Learning Internship**

---

## 📌 Objective

Build a machine learning **regression model** to predict the aggregate rating of a restaurant (0–5 scale) based on its features such as cuisine type, location, price range, and service offerings.

---

## 📂 Notebook

`Task1_Predict_Restaurant_Ratings.ipynb`

---

## 🔄 Workflow

```
Raw Dataset
    │
    ▼
1. Data Loading          → 9,551 restaurants × 21 features
    │
    ▼
2. Preprocessing
   ├─ Handle 9 missing values in 'Cuisines' column
   ├─ Label-encode City (top 20 cities, rest → 'Other')
   ├─ Label-encode Country Code
   └─ Engineer 'Cuisine_count' feature
    │
    ▼
3. Feature Selection     → 9 features selected
    │
    ▼
4. Train/Test Split      → 80% train (5,922) / 20% test (1,481)
    │
    ▼
5. Model Training        → 5 regression models
    │
    ▼
6. Evaluation            → RMSE, MAE, R²
    │
    ▼
7. Feature Importance    → Top drivers identified
```

---

## 🧠 Features Used

| Feature | Description |
|---------|-------------|
| `Average Cost for two` | Price indicator |
| `Price range` | Categorical tier (1–4) |
| `Votes` | Number of user votes |
| `Has Table booking` | Binary (0/1) |
| `Has Online delivery` | Binary (0/1) |
| `Is delivering now` | Binary (0/1) |
| `City_enc` | Label-encoded city |
| `Country_enc` | Label-encoded country |
| `Cuisine_count` | Number of cuisines offered |

> **Note:** Only restaurants with a non-zero rating (7,403 records) were used for model training to avoid bias from unrated entries.

---

## 🤖 Models Trained

| Model | Scaling Used |
|-------|-------------|
| Linear Regression | ✅ StandardScaler |
| Ridge Regression (α=1.0) | ✅ StandardScaler |
| Decision Tree (max_depth=8) | ❌ Raw features |
| Random Forest (100 trees, max_depth=10) | ❌ Raw features |
| **Gradient Boosting** (100 estimators, max_depth=5) | ❌ Raw features |

---

## 📊 Results

| Model | MSE | RMSE ↓ | MAE ↓ | R² ↑ |
|-------|-----|---------|-------|------|
| **Gradient Boosting** ⭐ | 0.1210 | **0.3478** | **0.2576** | **0.6089** |
| Random Forest | 0.1250 | 0.3535 | 0.2611 | 0.5959 |
| Decision Tree | 0.1316 | 0.3628 | 0.2697 | 0.5744 |
| Ridge Regression | 0.1904 | 0.4363 | 0.3420 | 0.3845 |
| Linear Regression | 0.1904 | 0.4363 | 0.3420 | 0.3845 |

### 🏆 Best Model: **Gradient Boosting**
- R² Score: **0.6089** (explains ~61% of rating variance)
- RMSE: **0.3478** (predictions within ±0.35 rating points on average)

---

## 🔑 Key Insights

1. **Votes is the strongest predictor** — restaurants with more engagement tend to earn higher ratings
2. **Price range matters** — premium restaurants (tier 3–4) consistently score higher
3. **City encodes local standards** — dining culture varies significantly by location
4. **Ensemble methods dominate** — tree-based ensembles (RF, GBM) far outperform linear models
5. **Cuisine count is weakly predictive** — offering more cuisines doesn't strongly impact ratings

---

## 📈 Generated Plots

| File | Description |
|------|-------------|
| `plots/task1_model_comparison.png` | R², RMSE, MAE comparison bar charts |
| `plots/task1_feature_importance.png` | Gradient Boosting feature importances |
| `plots/task1_actual_vs_predicted.png` | Predicted vs. actual rating scatter |
| `plots/task1_correlation.png` | Feature correlation heatmap |

---

## ▶️ How to Run

1. Open `Task1_Predict_Restaurant_Ratings.ipynb` in Jupyter
2. Ensure `Dataset .csv` is in the same directory
3. Run all cells top-to-bottom (`Kernel → Restart & Run All`)

---

*Part of the Cognifyz Technologies ML Internship Project*
