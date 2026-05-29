# Task 2 — Restaurant Recommendation System 💡

**Cognifyz Technologies — Machine Learning Internship**

---

## 📌 Objective

Design and implement a **content-based filtering recommendation system** that suggests restaurants to users based on their preferences for cuisine, price range, city, and service features.

---

## 📂 Notebook

`Task2_Restaurant_Recommendation.ipynb`

---

## 🔄 Workflow

```
Raw Dataset
    │
    ▼
1. Data Loading          → 9,551 restaurants
    │
    ▼
2. Preprocessing
   ├─ Fill missing 'Cuisines', 'City', 'Locality' values
   └─ Encode binary service columns (Yes/No → 1/0)
    │
    ▼
3. Recommendation Criteria Definition
   ├─ Cuisine Preference  (TF-IDF on Cuisines + Locality text)
   ├─ Price Range         (Filter: 1=Budget → 4=Luxury)
   ├─ City                (Optional location filter)
   └─ Services            (Table booking / Online delivery flags)
    │
    ▼
4. Content-Based Filtering
   ├─ TF-IDF Vectorization on combined text features
   ├─ Cosine Similarity matrix computation
   └─ Rank & filter by user-specified criteria
    │
    ▼
5. System Testing        → Sample user queries evaluated
    │
    ▼
6. Quality Evaluation    → Recommendation metrics computed
```

---

## 🧠 Recommendation Engine Design

### Content-Based Filtering Approach

The system represents each restaurant as a **feature vector** based on its textual and categorical attributes. Similarity between restaurants is measured using **cosine similarity** on TF-IDF encoded text features.

```
User Preferences
    │
    ├─ Cuisine: "Indian"
    ├─ Max Price Range: 2
    ├─ City: "New Delhi"
    └─ Requires Online Delivery: True
         │
         ▼
    Filter → Similarity Rank → Top-N Results
```

### Criteria Supported

| Criterion | Encoding | Description |
|-----------|---------|-------------|
| **Cuisine Preference** | TF-IDF + Cosine Similarity | Match restaurants with similar cuisine profiles |
| **Price Range** | Hard Filter | 1 (Budget) → 2 (Moderate) → 3 (Expensive) → 4 (Luxury) |
| **City / Location** | Hard Filter | Filter by city name |
| **Table Booking** | Binary Flag | Require or allow table reservations |
| **Online Delivery** | Binary Flag | Require or allow delivery |

---

## 📊 Similarity Matrix

The cosine similarity matrix captures cuisine-based similarity between all restaurants. Restaurants with identical or very similar cuisine profiles receive similarity scores close to **1.0**.

---

## 🎯 Sample Recommendation Query

```python
User Preferences:
  - Cuisine     : "North Indian"
  - Price Range : ≤ 3
  - City        : "New Delhi"
  - Delivery    : Required

→ System Returns Top-5 Similar Restaurants with:
   Restaurant Name | City | Cuisines | Price | Rating | Votes
```

---

## 🔑 Key Insights

1. **TF-IDF captures cuisine nuance** — restaurants offering "North Indian, Chinese" are similar but distinct from "Chinese, North Indian" — weighted by term frequency
2. **Price range is a hard constraint** — most users have a clear budget ceiling
3. **City filtering improves relevance** — local context is crucial for practical recommendations
4. **Service flags add personalization** — table booking and delivery preferences vary significantly by user type
5. **Votes as secondary ranking** — among equally similar restaurants, higher-voted ones are ranked first

---

## 📈 Generated Plots

| File | Description |
|------|-------------|
| `plots/task2_criteria_overview.png` | Dataset overview: cuisine and price distributions |
| `plots/task2_similarity_heatmap.png` | Cosine similarity heatmap (restaurant subset) |
| `plots/task2_recommendation_quality.png` | Recommendation quality metrics visualization |

---

## ▶️ How to Run

1. Open `Task2_Restaurant_Recommendation.ipynb` in Jupyter
2. Ensure `Dataset .csv` is in the same directory
3. Run all cells top-to-bottom (`Kernel → Restart & Run All`)
4. Modify the **user preference dictionary** in the last section to test custom recommendations

---

*Part of the Cognifyz Technologies ML Internship Project*
