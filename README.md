# 🎬 Movie Recommendation & Clustering System

This project builds a complete end-to-end system for **exploring**, **recommending**, and **clustering** movies using both structured metadata and natural language processing (NLP) techniques. The dataset was sourced from [Kaggle - Movie Dataset by Ehab Abdelkarim](https://www.kaggle.com/code/ehababdelkarim/movie-dataset).

---

## 📌 Project Pipeline

### ✅ Step 1: Data Exploration
- Explored dataset structure and missing values
- Analyzed data types and descriptive statistics
- Created a function to quickly summarize the dataset

### ✅ Step 2: Data Cleaning
- Handled missing values with **group-based median and mode imputation**
- Filled in missing companies and dropped sparse records
- Visualized missingness with `missingno`

### ✅ Step 3: Feature Engineering
- Created new features:
  - `profit`, `roi`, `log_votes`
  - `runtime_category` (Short, Standard, Long)
  - `released_month`, `released_year`
  - `top_director`, `top_star`, `top_writer` (Top 10 only)
- Capped ROI outliers using IQR + winsorization

### ✅ Step 4: Exploratory Data Analysis (EDA)
- Numeric distribution visualizations: histograms, KDE, violin plots
- Outlier detection with IQR and boxenplots
- Categorical distribution analysis by `genre`, `rating`, and `month`
- Correlation heatmap and scatterplots (e.g., budget vs gross)

### ✅ Step 5: Text Vectorization
- Cleaned and combined `title + genre` into `combo_text`
- Applied **TF-IDF Vectorization**
- Inspected token frequency and matrix dimensions

### ✅ Step 6: Movie Recommender System
- Implemented **hybrid movie recommendation** using cosine similarity on TF-IDF of `combo_text`
- Built a recommendation function:
  ```python
  def recommend_hybrid(title, top_n=5)

## 🎬 Example Use Case

**Input Movie:** `"The Matrix"`  
**Hybrid Recommender Output:** Suggests other sci-fi/action films based on **semantic similarity** using title + genre TF-IDF.

---

## ✅ Step 7: Movie Clustering

- Applied **unsupervised learning** with:
  - `KMeans`, `MiniBatchKMeans`, and `DBSCAN`
- Used a custom pipeline:
  - `TruncatedSVD` for dimensionality reduction
  - `StandardScaler` for feature normalization
- Reduced dimensionality for better interpretability
- Visualized clusters in 3D using `plotly.express`

---

## ✅ Cluster Interpretation

- Profiled **top genres** and **example movies** per cluster
- Assigned **human-readable cluster names**:

| Cluster ID | Description                             |
|------------|------------------------------------------|
| 🎭         | Light Entertainment / Comedy Mix         |
| 👻         | Dark Horror & Thriller                   |
| 🎬         | Serious Storytelling & Dramas            |
| 🔫         | Real-Life Action Epics                   |
| 🎥         | Stylized Crime-Comedy Hybrids            |
| 🕵️         | Gritty Crime and Action Thrillers        |

---

## 💼 Business Applications

- ✅ **Content-based filtering**
- ✅ **Marketing segmentation**
- ✅ **Automated content tagging**
- ✅ **Library balancing** for streaming services

---

## 📁 Dataset Info

| Feature    | Description                              |
|------------|------------------------------------------|
| `name`     | Movie title                              |
| `genre`    | Primary genre                            |
| `rating`   | MPAA rating (e.g., PG-13, R)             |
| `year`     | Release year                             |
| `score`    | IMDb rating                              |
| `votes`    | Number of IMDb votes                     |
| `director` | Director name                            |
| `writer`   | Screenwriter name                        |
| `star`     | Lead actor/actress                       |
| `budget`   | Estimated production budget (USD)        |
| `gross`    | Gross box office earnings (USD)          |
| `runtime`  | Duration in minutes                      |
| `country`  | Country of production                    |

---

## 🚀 Technologies Used

- 🐍 **Python**, **Pandas**, **NumPy**
- 📊 **Seaborn**, **Matplotlib**, **Plotly**
- 🧠 **Scikit-learn**: TF-IDF, KMeans, TruncatedSVD, Pipelines
- 🗣️ **NLP**: Text preprocessing, vectorization, cosine similarity
- 🧱 **Missingno**: Visualizing missing values

---

## 🧠 Author

**Reza Zare**  
*Data Scientist | NLP + Clustering Enthusiast*  
🔗 [GitHub](https://github.com/arezazare)  

---

## 📜 License

This project is licensed under the **MIT License** — feel free to use, modify, and build on it.
