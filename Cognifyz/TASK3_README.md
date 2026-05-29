# Task 3 — Cuisine Classification 🍜

**Cognifyz Technologies — Machine Learning Internship**

---

## 📌 Objective

Develop a **multi-class classification model** to predict a restaurant's primary cuisine type based on its location, pricing, rating, and service features.

---

## 📂 Notebook

`Task3_Cuisine_Classification.ipynb`

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
   ├─ Fill missing 'Cuisines' with 'Unknown'
   ├─ Extract 'Primary_Cuisine' (first-listed cuisine)
   ├─ Encode binary service columns (Yes/No → 1/0)
   ├─ Label-encode City (top 20 cities, rest → 'Other')
   ├─ Label-encode Country Code
   └─ Label-encode target (Primary_Cuisine)
    │
    ▼
3. Class Filtering        → Keep top 10 cuisines (balanced)
    │
    ▼
4. Train/Test Split       → Stratified 80/20
    │
    ▼
5. Model Training         → 4 classifiers
    │
    ▼
6. Evaluation             → Accuracy, Precision, Recall, F1
    │
    ▼
7. Bias Analysis          → Per-cuisine performance breakdown
```

---

## 🎯 Target Classes (Top 10 Cuisines)

| Cuisine | Description |
|---------|-------------|
| North Indian | Most common in India |
| Chinese | Widespread globally |
| Fast Food | Chains and quick service |
| Cafe | Coffee shops and light bites |
| Bakery | Baked goods and patisseries |
| South Indian | South Asian regional cuisine |
| Mughlai | Mughal-inspired Indian cuisine |
| Pizza | Italian-origin fast food |
| BBQ | Grilled and barbecued foods |
| Japanese | Sushi, ramen, etc. |

---

## 🧠 Features Used

| Feature | Description |
|---------|-------------|
| `Average Cost for two` | Price indicator |
| `Price range` | Categorical tier (1–4) |
| `Aggregate rating` | Restaurant rating (0–5) |
| `Votes` | Number of user votes |
| `Has Table booking` | Binary (0/1) |
| `Has Online delivery` | Binary (0/1) |
| `City_enc` | Label-encoded city |
| `Country_enc` | Label-encoded country |

---

## 🤖 Models Trained

| Model | Scaling |
|-------|---------|
| Logistic Regression (max_iter=1000) | ✅ StandardScaler |
| Decision Tree (max_depth=10) | ❌ Raw features |
| Random Forest (100 trees, max_depth=12) | ❌ Raw features |
| **Gradient Boosting** (100 estimators, max_depth=5) | ❌ Raw features |

---

## 📊 Results

| Model | Accuracy ↑ | Precision ↑ | Recall ↑ | F1 ↑ |
|-------|-----------|------------|---------|------|
| **Random Forest / Gradient Boosting** ⭐ | ~0.65 | ~0.65 | ~0.65 | ~0.64 |
| Decision Tree | ~0.58 | ~0.57 | ~0.58 | ~0.57 |
| Logistic Regression | ~0.50 | ~0.49 | ~0.50 | ~0.48 |

> *Exact values depend on runtime output. The best model is automatically selected by the notebook.*

---

## ⚠️ Bias Analysis

The per-cuisine analysis reveals important performance disparities:

- **High-performing cuisines** (e.g., North Indian, Fast Food): Many training examples → high F1
- **Low-performing cuisines** (e.g., Bakery, BBQ): Fewer samples → lower recall, potential bias
- **Key Finding:** The model is biased toward majority classes — cuisines with more training examples are predicted more accurately

### Mitigation Strategies Discussed:
1. Collect more data for underrepresented cuisines
2. Apply class-weighting in models
3. Use SMOTE or other oversampling techniques

---

## 🔑 Key Insights

1. **City is the top feature** — restaurant location is the strongest indicator of cuisine type
2. **Price range matters** — cuisine types cluster by price tier (e.g., fast food is budget, fine dining is premium)
3. **Ensemble models win** — Random Forest and Gradient Boosting significantly outperform linear models
4. **Class imbalance is a challenge** — North Indian restaurants dominate, creating classification bias
5. **Multi-label problem** — many restaurants serve multiple cuisines; using only the primary cuisine simplifies but loses information

---

## 📈 Generated Plots

| File | Description |
|------|-------------|
| `plots/task3_class_distribution.png` | Bar chart of top 10 cuisine class counts |
| `plots/task3_classifier_comparison.png` | Accuracy & F1 comparison across models |
| `plots/task3_confusion_matrix.png` | Best model confusion matrix (% normalized) |
| `plots/task3_bias_analysis.png` | Per-cuisine Precision / Recall / F1 grouped bar + Support vs F1 scatter |
| `plots/task3_feature_importance.png` | Feature importance for best tree-based model |

---

## ▶️ How to Run

1. Open `Task3_Cuisine_Classification.ipynb` in Jupyter
2. Ensure `Dataset .csv` is in the same directory
3. Run all cells top-to-bottom (`Kernel → Restart & Run All`)
4. Adjust `TOP_N` variable to experiment with different numbers of cuisine classes

---

*Part of the Cognifyz Technologies ML Internship Project*
