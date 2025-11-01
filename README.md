# 🧠 Data Mining Implementation Project (2024–2025)

### Authors  
**Konstantinos Vasiladiotis (AM: 1088094)**  
**Angelos Kondalis (AM: 1095483)**  

---

## 📘 Overview  
This project was developed as part of the **Data Mining course (2024–2025)**.  
It focuses on analyzing a large dataset and applying various **data preprocessing**, **clustering**, and **classification** techniques to predict the **“Label”** column (Malicious or Benign).

Due to the dataset’s large size (~5GB), we employed sampling and clustering methods to create smaller, representative subsets that maintain the statistical balance between the classes.

All work was implemented using **Anaconda Navigator** and **Jupyter Notebook**.

---

## ⚙️ Technologies & Libraries  

| Category | Tools |
|-----------|--------|
| Data Manipulation | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn` |
| Machine Learning | `sklearn`, `tensorflow`, `keras` |
| Environment | `Anaconda Navigator`, `Jupyter Notebook` |

---

## 🧩 Dataset Handling  

The dataset was initially too large to load directly with Pandas.  
To overcome this, we:
- Applied **sampling** by keeping all rare samples while reducing the frequency of overrepresented ones.  
- Ensured the **malicious/benign ratio** remained consistent after sampling.  
- Conducted exploratory analysis using:
  - `df.head()`, `df.info()`, `df.describe()`
  - `value_counts()` for class balance
  - Correlation and heatmap visualizations for feature relevance.

---

## 🔍 Data Analysis & Feature Selection  

### Objective:
Identify the most relevant features that affect the target variable (“Label”).

We used:
- **Correlation analysis** to detect relationships between features.  
- **Outlier detection** to remove misleading data points.  
- **Feature ranking** to select the top 15 most influential columns.

This resulted in a refined dataframe (`df_new`) containing only the most meaningful attributes.

---

## 🧮 Data Reduction Techniques  

Three reduced datasets were created:

1. **Random Sampling (`df_sampled`)** – simple random subset.  
2. **BIRCH Clustering (`df_birch`)** – memory-efficient summarization via clustering tree.  
3. **DBSCAN Clustering (`df_dbscan`)** – density-based clustering resistant to noise and outliers.

### Why BIRCH and DBSCAN?
- **BIRCH:** Efficient for large datasets, requires low memory, and can adapt to unknown cluster counts.  
- **DBSCAN:** Ideal for real-world data, identifies dense regions, and naturally excludes outliers as noise.  

---

## 🤖 Machine Learning Models  

We trained and evaluated two models using the reduced datasets:

### 1. **Support Vector Machine (SVM)**
Each dataset was split into train/test sets and normalized.  
Results showed:
- **High accuracy (up to 100%)**
- **Best performance with DBSCAN dataset**
- Evaluation metrics included:
  - Confusion Matrix  
  - Precision, Recall, and F1-score  

### 2. **Neural Network (Keras)**
A neural classifier was trained on the same datasets.  
The **DBSCAN** and **BIRCH** sets again achieved superior results with nearly perfect predictions, outperforming the simple sampled subset.

---

## 📊 Results Summary  

| Dataset | Best Model | Accuracy | Notes |
|----------|-------------|-----------|--------|
| `df_sampled` | SVM / NN | ~98% | Slightly more misclassifications |
| `df_birch` | SVM / NN | ~99% | Excellent performance |
| `df_dbscan` | SVM / NN | ~100% | Best overall model |

---

## 🏁 Conclusions  

- Sampling and clustering significantly improved data handling for large datasets.  
- Both **SVM** and **Neural Networks** performed extremely well, with **DBSCAN-based preprocessing** yielding the best results.  
- The project demonstrates effective **feature reduction**, **noise handling**, and **classification accuracy** for imbalanced cybersecurity-related data.

---



## 🧠 Key Learning Outcomes  

- Managing large-scale datasets efficiently.  
- Applying advanced clustering (BIRCH, DBSCAN).  
- Building and evaluating classification models.  
- Understanding dataset imbalance and sampling strategies.  

---

## 🪪 License  
This project is for **educational purposes only**.  
All rights reserved © 2025 – *University of Patras, Data Mining Course.*
