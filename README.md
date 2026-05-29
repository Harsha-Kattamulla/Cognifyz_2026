# 🍽️ Cognizify — Restaurant Analytics & ML Internship Project

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=for-the-badge&logo=pandas&logoColor=white)

**Machine Learning Internship — Cognifyz Technologies**

*A comprehensive end-to-end restaurant data analytics and machine learning project covering regression, recommendation systems, classification, and geospatial analysis.*

</div>

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Project Structure](#-project-structure)
- [Tasks Summary](#-tasks-summary)
- [Results & Key Findings](#-results--key-findings)
- [Installation & Setup](#-installation--setup)
- [How to Run](#-how-to-run)
- [Visualizations](#-visualizations)
- [Technologies Used](#-technologies-used)
- [Author](#-author)

---

## 🎯 Project Overview

This repository contains the complete implementation of the **Cognifyz Technologies Machine Learning Internship** project. The project applies a wide range of supervised and unsupervised machine learning techniques to a real-world restaurant dataset, delivering actionable insights across four distinct analytical tasks:

| Task | Type | Objective |
|------|------|-----------|
| **Task 1** | Regression | Predict restaurant aggregate ratings |
| **Task 2** | Recommendation | Build a content-based restaurant recommender |
| **Task 3** | Classification | Classify restaurants by cuisine type |
| **Task 4** | Geospatial | Location-based restaurant analysis |

---

## 📊 Dataset

| Property | Value |
|----------|-------|
| **File** | `Dataset .csv` |
| **Records** | 9,551 restaurants |
| **Features** | 21 columns |
| **Coverage** | 15 countries, multiple cities |

### Key Columns

| Column | Description |
|--------|-------------|
| `Restaurant Name` | Name of the restaurant |
| `City` / `Locality` | Location information |
| `Latitude` / `Longitude` | Geographic coordinates |
| `Cuisines` | Type(s) of cuisine served |
| `Average Cost for two` | Price indicator |
| `Price range` | Categorical price tier (1–4) |
| `Aggregate rating` | Target variable (0–5 scale) |
| `Votes` | Number of user votes |
| `Has Table booking` | Table reservation availability |
| `Has Online delivery` | Online ordering availability |

---

## 📁 Project Structure

```
Cognizify/
│
├── 📓 Task1_Predict_Restaurant_Ratings.ipynb    # Regression task
├── 📓 Task2_Restaurant_Recommendation.ipynb     # Recommendation system
├── 📓 Task3_Cuisine_Classification.ipynb        # Multi-class classification
├── 📓 Task4_Location_Based_Analysis.ipynb       # Geospatial analysis
│
├── 📊 Dataset .csv                              # Main dataset
├── 📄 Machine Learning.pdf                      # Reference material
│
├── 📁 plots/                                    # All generated visualizations
│   ├── task1_model_comparison.png
│   ├── task1_feature_importance.png
│   ├── task1_actual_vs_predicted.png
│   ├── task1_correlation.png
│   ├── task2_criteria_overview.png
│   ├── task2_similarity_heatmap.png
│   ├── task2_recommendation_quality.png
│   ├── task3_class_distribution.png
│   ├── task3_classifier_comparison.png
│   ├── task3_confusion_matrix.png
│   ├── task3_bias_analysis.png
│   ├── task3_feature_importance.png
│   ├── task4_global_map.png
│   ├── task4_location_maps.png
│   ├── task4_concentration.png
│   ├── task4_city_statistics.png
│   ├── task4_city_insights_bubble.png
│   ├── task4_country_analysis.png
│   └── task4_city_price_heatmap.png
│
└── 📄 README.md                                 # This file
```

---

## 🔍 Tasks Summary

### Task 1 — Predict Restaurant Ratings ⭐
> **Goal:** Build regression models to predict a restaurant's aggregate rating.

- **Preprocessing:** Handled 9 missing cuisine values, label-encoded cities and countries, engineered a cuisine-count feature
- **Models:** Linear Regression, Ridge Regression, Decision Tree, Random Forest, **Gradient Boosting**
- **Best Model:** Gradient Boosting (R² = 0.61, RMSE = 0.35)
- **Top Features:** Votes, Price Range, City

### Task 2 — Restaurant Recommendation System 💡
> **Goal:** Build a content-based filtering recommendation engine.

- **Approach:** TF-IDF vectorization on cuisine and locality text, cosine similarity scoring
- **Criteria Supported:** Cuisine preference, price range, city, service flags (table booking, delivery)
- **Output:** Personalized top-N restaurant recommendations per user query

### Task 3 — Cuisine Classification 🍜
> **Goal:** Multi-class classification to predict a restaurant's primary cuisine.

- **Classes:** Top 10 cuisines (North Indian, Chinese, Fast Food, Cafe, etc.)
- **Models:** Logistic Regression, Decision Tree, Random Forest, **Gradient Boosting**
- **Best Model:** Random Forest / Gradient Boosting (~60–65% accuracy)
- **Key Finding:** City location and price range are the strongest predictors of cuisine type

### Task 4 — Location-Based Analysis 🌍
> **Goal:** Geospatial exploration of the restaurant landscape.

- **Coverage:** 9,551 restaurants across 15 countries
- **Key Insights:**
  - New Delhi alone accounts for >50% of all restaurants
  - Higher price range (3–4) consistently correlates with better ratings
  - South & Southeast Asia form the core geographic cluster
  - Locality concentration mirrors city-level patterns

---

## 📈 Results & Key Findings

### Model Performance (Task 1 — Regression)

| Model | RMSE | MAE | R² |
|-------|------|-----|-----|
| **Gradient Boosting** ⭐ | 0.3478 | 0.2576 | **0.6089** |
| Random Forest | 0.3535 | 0.2611 | 0.5959 |
| Decision Tree | 0.3628 | 0.2697 | 0.5744 |
| Ridge Regression | 0.4363 | 0.3420 | 0.3845 |
| Linear Regression | 0.4363 | 0.3420 | 0.3845 |

### Key Business Insights

- 🗳️ **Votes matter most** — restaurants with more votes consistently earn higher ratings
- 💰 **Price & quality correlate** — higher price range restaurants tend to be rated better
- 🌆 **Location is predictive** — city is a strong signal for both ratings and cuisine type
- 📍 **India dominates** — Country Code 1 (India) represents the vast majority of the dataset
- 🍽️ **Cuisine diversity** — multi-cuisine restaurants tend to attract more votes

---

## ⚙️ Installation & Setup

### Prerequisites

- Python 3.10 or higher
- pip package manager
- Jupyter Notebook or JupyterLab

### Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

Or install all at once:

```bash
pip install pandas>=1.5.0 numpy>=1.23.0 matplotlib>=3.6.0 seaborn>=0.12.0 scikit-learn>=1.1.0 jupyter
```

---

## ▶️ How to Run

1. **Clone or download** this repository
2. **Place the dataset** (`Dataset .csv`) in the project root directory
3. **Launch Jupyter Notebook:**

```bash
jupyter notebook
```

4. **Open and run** each notebook in order:
   - `Task1_Predict_Restaurant_Ratings.ipynb`
   - `Task2_Restaurant_Recommendation.ipynb`
   - `Task3_Cuisine_Classification.ipynb`
   - `Task4_Location_Based_Analysis.ipynb`

> **Note:** Each notebook is self-contained. Run all cells top-to-bottom. Plots are saved automatically to the `plots/` directory.

---

## 🖼️ Visualizations

All generated plots are stored in the `plots/` directory and include:

| Plot | Description |
|------|-------------|
| `task1_model_comparison.png` | Side-by-side R², RMSE, MAE comparison across models |
| `task1_feature_importance.png` | Gradient Boosting feature importance bar chart |
| `task1_actual_vs_predicted.png` | Scatter plot of predicted vs. actual ratings |
| `task1_correlation.png` | Feature correlation heatmap |
| `task2_similarity_heatmap.png` | Restaurant cosine similarity matrix |
| `task2_criteria_overview.png` | Dataset overview for recommendation criteria |
| `task3_confusion_matrix.png` | Best classifier confusion matrix (%) |
| `task3_bias_analysis.png` | Per-cuisine Support vs F1 bubble chart |
| `task3_classifier_comparison.png` | Accuracy & F1 across classifiers |
| `task4_global_map.png` | Global restaurant distribution map (dark background) |
| `task4_city_price_heatmap.png` | City × Price Range rating heatmap |
| `task4_city_insights_bubble.png` | Bubble chart: Cost vs Rating vs Count |

---

## 🛠️ Technologies Used

| Library | Version | Purpose |
|---------|---------|---------|
| **Python** | 3.10+ | Core programming language |
| **Pandas** | 2.x | Data loading and manipulation |
| **NumPy** | 1.23+ | Numerical computations |
| **Matplotlib** | 3.6+ | Static plotting and maps |
| **Seaborn** | 0.12+ | Statistical visualization |
| **scikit-learn** | 1.1+ | Machine learning models and metrics |
| **Jupyter Notebook** | — | Interactive development environment |

---

## 👤 Author

**Harsha**
*Machine Learning Intern — Cognifyz Technologies*

---

## 📄 License

This project is submitted as part of the Cognifyz Technologies Machine Learning Internship program. All analysis and code are original work by the author.

---

<div align="center">

*Made with ❤️ and 🐍 Python*

</div>
