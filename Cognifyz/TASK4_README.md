# Task 4 — Location-Based Analysis 🌍

**Cognifyz Technologies — Machine Learning Internship**

---

## 📌 Objective

Perform a comprehensive **geospatial and location-based analysis** of the restaurant dataset — mapping global distribution, identifying concentration hotspots, computing city/locality statistics, and uncovering patterns in how location relates to ratings, cost, and cuisine.

---

## 📂 Notebook

`Task4_Location_Based_Analysis.ipynb`

---

## 🔄 Workflow

```
Raw Dataset
    │
    ▼
1. Data Loading          → 9,551 restaurants across 15 countries
    │
    ▼
2. Coordinate Exploration
   ├─ Validate lat/lon ranges (−90 to 90, −180 to 180)
   └─ Remove invalid (0, 0) coordinate entries
    │
    ▼
3. Geographic Visualization
   ├─ Global restaurant map (colored by rating)
   └─ Dual map (by rating & by price range)
    │
    ▼
4. Concentration Analysis
   ├─ Top 15 cities by restaurant count
   └─ Top 20 localities by restaurant count
    │
    ▼
5. Statistical Analysis
   ├─ City-level aggregations (avg rating, cost, price range, top cuisine)
   └─ Locality-level aggregations
    │
    ▼
6. Insight Discovery
   ├─ Bubble chart: Cost vs Rating vs Count vs Price Level
   ├─ Country-level analysis (count + avg rating)
   └─ City × Price Range heatmap
```

---

## 🗺️ Geographic Coverage

| Metric | Value |
|--------|-------|
| **Total Restaurants** | 9,551 |
| **Countries** | 15 |
| **Unique Cities** | ~140+ |
| **Unique Localities** | ~1,000+ |

### Countries Represented

| Code | Country |
|------|---------|
| 1 | 🇮🇳 India |
| 14 | 🇦🇺 Australia |
| 30 | 🇧🇷 Brazil |
| 37 | 🇨🇦 Canada |
| 94 | 🇮🇩 Indonesia |
| 148 | 🇳🇿 New Zealand |
| 162 | 🇵🇭 Philippines |
| 166 | 🇶🇦 Qatar |
| 184 | 🇸🇬 Singapore |
| 189 | 🇿🇦 South Africa |
| 191 | 🇱🇰 Sri Lanka |
| 208 | 🇹🇷 Turkey |
| 214 | 🇦🇪 UAE |
| 215 | 🇬🇧 UK |
| 216 | 🇺🇸 USA |

---

## 📊 Key Statistics

### Top Cities by Restaurant Count

| City | Count | Share |
|------|-------|-------|
| **New Delhi** | 5,473+ | ~57% |
| Gurgaon | ~1,120 | ~12% |
| Noida | ~1,050 | ~11% |
| *Others* | ~1,900 | ~20% |

### City-Level Metrics (Cities with 50+ restaurants)

| Metric | Description |
|--------|-------------|
| `Restaurant_Count` | Total restaurants in city |
| `Avg_Rating` | Mean aggregate rating |
| `Avg_Cost` | Mean average cost for two |
| `Avg_Price_Range` | Mean price tier (1–4) |
| `Avg_Votes` | Mean number of votes |
| `Top_Cuisine` | Most common primary cuisine |

---

## 💡 Key Insights & Patterns

### 1. Geographic Concentration
> **India dominates** — with New Delhi alone accounting for over 50% of all restaurants in the dataset. The geographic center of mass is firmly in South Asia.

### 2. Price × Rating Correlation
> **Higher price range correlates with better ratings** across most cities. Luxury restaurants (tier 3–4) consistently outrate budget options (tier 1–2).

### 3. Small City Advantage
> **Smaller cities tend to have fewer but higher-rated restaurants** — possibly due to lower competition and more focused food culture.

### 4. Locality Hotspots
> Locality concentration mirrors city patterns — specific neighborhoods (e.g., Connaught Place, Koramangala) act as **local restaurant hotspots** with significantly above-average density.

### 5. Country-Level Patterns
> While India dominates in count, countries like **Philippines, Singapore, and UAE** show competitive average ratings, suggesting high dining standards despite smaller sample sizes.

### 6. Cost ≠ Count
> The bubble chart reveals cities with high restaurant density don't always have the highest average costs — dining culture and local economics vary significantly.

---

## 📈 Generated Plots

| File | Description |
|------|-------------|
| `plots/task4_global_map.png` | Dark-themed global scatter map, colored by rating |
| `plots/task4_location_maps.png` | Side-by-side: By Rating & By Price Range |
| `plots/task4_concentration.png` | Top 15 cities & Top 20 localities by count |
| `plots/task4_city_statistics.png` | Avg Rating, Avg Cost, Avg Price Range by city |
| `plots/task4_city_insights_bubble.png` | Bubble chart: Cost vs Rating (size=count, color=price) |
| `plots/task4_country_analysis.png` | Restaurant count & avg rating by country |
| `plots/task4_city_price_heatmap.png` | Heatmap: Avg Rating by City × Price Range |

---

## ▶️ How to Run

1. Open `Task4_Location_Based_Analysis.ipynb` in Jupyter
2. Ensure `Dataset .csv` is in the same directory
3. Run all cells top-to-bottom (`Kernel → Restart & Run All`)

> **Tip:** The global map (`task4_global_map.png`) uses a dark background theme — best viewed in full resolution.

---

*Part of the Cognifyz Technologies ML Internship Project*
