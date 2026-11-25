# 🍷 Wine Dataset Analysis & Machine Learning Exploration 📊

Welcome to the **Wine Dataset Analysis & Machine Learning Exploration** project! 🚀 This repository contains end-to-end exploratory data analysis (EDA), unsupervised learning (clustering & dimensionality reduction), and machine learning workflows built on Scikit-Learn's classic Wine recognition dataset.

---

## 📌 Project Overview

The objective of this project is to analyze chemical characteristics of wines grown in the same region in Italy across three different cultivars, and apply machine learning algorithms to:
- 🧪 **Analyze & Preprocess**: Explore distributions and standardize 13 continuous chemical attributes.
- 🔍 **Cluster & Segment**: Group wine samples using unsupervised learning (**K-Means** & **Hierarchical Clustering**).
- 📉 **Dimensionality Reduction**: Compress high-dimensional chemical feature space using **Principal Component Analysis (PCA)** for 2D and 3D visualization.
- 🎯 **Evaluate Performance**: Measure clustering quality using **Silhouette Analysis** and assess information retention via **Explained Variance Ratio**.

---

## 📂 Project Structure

```bash
Week3-Tasks/
├── task3.ipynb        # 📓 Jupyter Notebook containing EDA, preprocessing, clustering & PCA
└── README.md          # 📖 Project documentation
```

---

## 🍇 Dataset Description

The dataset used is the **Wine Dataset** from `sklearn.datasets.load_wine`.
- **Instances:** 178 samples 🏷️
- **Target Classes:** 3 Cultivars (Class 0, Class 1, Class 2) 🍷
- **Attributes:** 13 chemical features:
  1. `alcohol` 🍾
  2. `malic_acid` 🍏
  3. `ash` 🌫️
  4. `alcalinity_of_ash` 🧪
  5. `magnesium` 💊
  6. `total_phenols` 🌿
  7. `flavanoids` 🪻
  8. `nonflavanoid_phenols` 🔬
  9. `proanthocyanins` 🧬
  10. `color_intensity` 🎨
  11. `hue` 🌈
  12. `od280/od315_of_diluted_wines` 🧪
  13. `proline` 🌾

---

## ⚙️ Methodology & Pipeline

### 1. 🧹 Data Exploration & Preprocessing
- Inspection of dataset shape (`178 x 14`), schema, missing values, and descriptive statistics.
- Feature separation (`X`) and scaling using `StandardScaler` to ensure zero mean and unit variance across all features.

### 2. 🧩 Unsupervised Clustering
- **K-Means Clustering (`n_clusters=3`)**:
  - Partitions wine samples into 3 clusters based on Euclidean distance in scaled feature space.
  - **Silhouette Score**: `~0.2849`
- **Hierarchical / Agglomerative Clustering (`n_clusters=3`)**:
  - Builds nested clusters using bottom-up linkage.
  - **Silhouette Score**: `~0.2774`

### 3. 📉 Dimensionality Reduction (PCA)
- **2D PCA (`n_components=2`)**:
  - Retains ~**55.41%** total explained variance (`PC1: 36.20%`, `PC2: 19.21%`).
- **3D PCA (`n_components=3`)**:
  - Captures an additional dimension for richer representation and higher information retention.

---

## 🛠️ Tech Stack & Dependencies

- 🐍 **Python 3.x**
- 🐼 **Pandas**: Data manipulation & analysis
- 🔢 **NumPy**: Numerical computing
- 🤖 **Scikit-Learn**: Machine learning, preprocessing, clustering, PCA, and metrics
- 📊 **Matplotlib**: Visualizations and plotting

To install all required packages:
```bash
pip install numpy pandas scikit-learn matplotlib jupyter
```

---

## 🚀 How to Run

1. **Clone or Navigate to the Directory**:
   ```bash
   cd Week3-Tasks
   ```
2. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook task3.ipynb
   ```
3. **Execute the Cells**: Run cells sequentially from top to bottom.

---

## 💡 Key Takeaways & Highlights

- ⚖️ **Feature Standardization is Essential**: Because features like `proline` and `magnesium` have much wider ranges than `hue` or `nonflavanoid_phenols`, scaling ensures fair contribution across all attributes.
- 🎯 **Clustering Validation**: Both K-Means and Agglomerative Clustering naturally discover patterns that align closely with the 3 underlying cultivars.
- 🌌 **Information Compression**: PCA effectively collapses 13 dimensions into 2 or 3 components, retaining over 55% of the total variance for visualization.

