# 🛒 Wholesale Customer Segmentation Using Machine Learning
### *K-Means, Hierarchical Clustering, PCA, Silhouette Analysis & Feature Engineering*

---

## 📌 Project Overview

This project focuses on **customer segmentation** using **Unsupervised Machine Learning** techniques to understand customer purchasing behavior from the *Wholesale Customers Dataset*.  
The goal is to help businesses with:

- 🎯 Targeted marketing  
- 🏪 Inventory planning  
- 👥 Customer profiling  
- 📊 Strategic decision-making  

The complete pipeline includes:

- Exploratory Data Analysis (EDA)  
- Data preprocessing & scaling  
- K-Means clustering  
- Agglomerative (Hierarchical) clustering  
- PCA-based visualization  
- Silhouette score validation  
- Feature engineering for cluster insights  

---

## 📂 Dataset Description

The dataset includes **annual spending** by customers across six product categories:

| Feature | Description |
|--------|-------------|
| **Fresh** | Fresh products spend |
| **Milk** | Milk products spend |
| **Grocery** | Grocery spend |
| **Frozen** | Frozen products spend |
| **Detergents_Paper** | Cleaning materials spend |
| **Delicassen** | Delicacy items spend |
| **Channel** | 1 = Horeca, 2 = Retail |
| **Region** | 1 = Lisbon, 2 = Oporto, 3 = Other |

Total records: **440 customers**

---

## 🔍 1. Exploratory Data Analysis (EDA)

### 📊 Boxplots  
- Revealed **outliers** in all categories  
- Grocery & Detergents_Paper showed extreme high-value customers  

### 📉 Histograms  
- All features show **right-skewed distributions**  
- Most customers spend less; a few spend significantly more  

### 🔥 Correlation Heatmap  
- Strong correlation:  
  **Grocery ↔ Detergents_Paper (0.92)**  
- Indicates shared purchase behavior  

### 🔬 Pairplots  
- Visualized relationships between spending features  
- Suggested natural customer groupings  

---

## ⚙️ 2. Data Preprocessing

### 🧮 Standard Scaling  
K-Means uses Euclidean distance — scaling is necessary.

Formula:
\[
z = \frac{x - \mu}{\sigma}
\]

This ensures all spending features contribute equally to clustering.

---

## 🔢 3. Optimal Cluster Selection

### 📌 Elbow Method  
- WCSS drops sharply until **k = 3**  
- “Elbow” observed at **k = 3**

### 📌 Silhouette Score  
- Highest score at **k = 3** (~0.46)  
- Confirms ideal number of clusters  

👉 **Chosen number of clusters = 3**

---

## 🤖 4. K-Means Clustering

K-Means was trained using 3 clusters, and cluster labels were added to the dataset.

### 🏷 Cluster Interpretation:
- **Cluster 0:** High Fresh spenders (Horeca-like customers)  
- **Cluster 1:** High Grocery & Detergents spend (Retail-type buyers)  
- **Cluster 2:** Low spenders (Small-scale or occasional buyers)

Centroids give a meaningful summary of customer behavior.

---

## 🎨 5. PCA Visualization

Applied **Principal Component Analysis (PCA)** to reduce 6 features into 2 dimensions.

- PCA1 vs PCA2 scatterplot shows distinct cluster separation  
- Improves interpretability and visual presentation  

---

## 🌲 6. Agglomerative (Hierarchical) Clustering

Performed hierarchical clustering using **Ward linkage**.

- Dendrogram visualizes merging of clusters  
- Produced 3 clusters but with lower separation quality  

---

## 📊 7. Silhouette Score Comparison

| Model | Silhouette Score |
|--------|------------------|
| **K-Means** | **0.6**,**0.5** |
| **Agglomerative** | **0.26** |

**Result:**  
K-Means provides better-separated and more meaningful clusters.

---

## 🧩 8. Feature Engineering (For Insight Enhancement)

Additional features were created to improve cluster interpretation:

- **TotalSpend** — sum of all product categories  
- **Fresh_per_Channel**, **Grocery_per_Channel**, **Milk_per_Channel**  
- **Region_Avg_Grocery**, **Region_Avg_Fresh**, **Region_Avg_Milk**  
- **Cluster label** added for profiling  
- **One-hot encoding** for Channel & Region

These features were **not used for clustering**, only for deeper insights.

---

## 📌 9. Key Insights

- Customers naturally fall into **3 meaningful groups**.  
- Horeca customers prioritize **Fresh and Frozen** items.  
- Retail customers purchase mostly **Grocery & Detergents**.  
- Strong correlations help predict joint buying behavior.  
- Feature-engineered attributes enhanced business interpretations.

---

## 🏁 Conclusion

- ✔ **K-Means (k = 3)** is the best segmentation model for this dataset  
- ✔ PCA confirms cluster separation  
- ✔ Agglomerative model provides comparison but performs worse  
- ✔ Enhanced features improve understanding of customer clusters  

This segmentation can help businesses in customer targeting, inventory management, and strategic planning.

---

## 🛠 Tech Stack

- Python  
- Pandas, NumPy  
- Seaborn, Matplotlib  
- Scikit-Learn  
- SciPy  
- Jupyter Notebook  

---

## 📎 Author  
**Manish Y M**  
Wholesale Customer Segmentation — Machine Learning Project  
