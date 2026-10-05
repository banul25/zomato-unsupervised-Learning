
# Zomato Restaurant Clustering & Sentiment Analysis 🍽️📊

An Unsupervised Machine Learning project designed to segment restaurants and analyze customer sentiments using Zomato metadata and review datasets from Hyderabad.

---

## 📌 Project Overview

This project focuses on extracting actionable insights for both Zomato and restaurant owners by:
1. **Restaurant Segmentation (Clustering):** Grouping restaurants based on cost, cuisine diversity, customer engagement, hygiene ratings, and text reviews.
2. **Sentiment Analysis:** Preprocessing customer review text to identify key sentiment trends and customer satisfaction metrics.

By identifying natural groupings and key drivers of customer feedback, the project provides data-driven recommendations to improve operational strategies and customer experience.

---

## 🛠️ Key Features & Methodology

### 1. Data Cleaning & Wrangling
- **Data Integration:** Merged metadata and review datasets on restaurant identifiers.
- **Handling Missing Values & Duplicates:** Cleaned missing entries across ratings, timings, and collections, and removed duplicate records.
- **Type Casting:** Converted cost (removing commas) and numerical ratings into appropriate quantitative formats.

### 2. Feature Engineering & Preprocessing
- **Text Processing (NLP):** Lowercasing, contraction expansion, removal of punctuation/digits/stopwords, tokenization, and lemmatization on the `Review` column.
- **Vectorization:** Applied **TF-IDF Vectorization** on lemmatized reviews and reduced dimensionality using **TruncatedSVD**.
- **Numerical Scaling:** Standardized numerical attributes (e.g., Cost, Picture Count, Review Length, Cuisine Count) using `StandardScaler`.
- **Handling Class Imbalance:** Utilized **SMOTE** to balance target categories for sentiment evaluations.

### 3. Machine Learning & Clustering Models
We evaluated three clustering techniques:
* **K-Means Clustering (Champion Model):** Optimized using the **Elbow Method** ($K=4$), achieving a **Silhouette Score of 0.51**, producing distinct and highly interpretable clusters.
* **DBSCAN:** Used for density-based clustering to filter noise and detect spatial outliers.
* **Hierarchical Clustering:** Explored dendrograms to analyze hierarchical relationships between restaurant types.

---

## 📊 Dataset Summary

The analysis was performed on two primary datasets:
- **Metadata Dataset:** Contains restaurant details including Name, Cost for Two, Cuisines, Collections, Timings, and Zomato Links.
- **Reviews Dataset:** Contains customer feedback, ratings, review timestamps, metadata (follower counts), and user-uploaded pictures.

---

## 💡 Key Business Insights

- **Cost vs. Rating:** Higher-cost restaurants exhibited a statistically significant higher average rating compared to budget options.
- **Cuisine Trends:** *North Indian* and *Chinese* are the most frequent cuisines offered.
- **Hygiene Focus:** Restaurants tagged with "Food Hygiene Rated" scored significantly higher in customer satisfaction.
- **Customer Tiers:** The K-Means model successfully segmented restaurants into actionable profiles such as *High-Engagement Premium*, *Budget-Friendly Popular*, and *Specialty Niche*.

---

## 🚀 Tech Stack & Libraries

- **Language:** Python 3
- **Data Manipulation:** `pandas`, `numpy`
- **Data Visualization:** `matplotlib`, `seaborn`
- **Machine Learning & NLP:** `scikit-learn`, `imbalanced-learn` (SMOTE)

---

## 📂 Project Structure

```text
├── data/
│   ├── Zomato Restaurant names and Metadata.csv
│   └── Zomato Restaurant reviews.csv
├── Zomato_Unsupervised_Learning.ipynb
└── README.md
```


# How to Run
# Clone this repository:

```Bash
git clone [https://github.com/banul25/EDA-project.git](https://github.com/banul25/EDA-project.git)
```
Open Zomato_Unsupervised_Learning.ipynb in Google Colab or Jupyter Notebook.

Upload the datasets to your directory/drive and run the cells sequentially.
