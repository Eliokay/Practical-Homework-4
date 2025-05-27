
# 🏠 Unsupervised Learning on WA Census Renters: Hidden Housing Patterns

## 🔍 Overview
This project explores **hidden patterns among renters aged 20–30** in Washington State using **unsupervised learning techniques**. Our goal was to understand who lives with roommates, who lives alone, and who might be struggling with housing affordability — all without predefined labels.

We used:
- 📊 **Principal Component Analysis (PCA)**
- 🎯 **K-Means Clustering**
- 🌳 **Hierarchical Clustering**
- 🔧 **Matrix Completion via SVD**

## 📁 Dataset
The dataset comes from the **2023 IPUMS USA Census Microdata** and was filtered to:
- Adults aged **20–30**
- Earning **>$40,000/year**
- Living in **rental homes with ≥2 bedrooms**

Link to source: [IPUMS USA - Version 16.0](https://doi.org/10.18128/D010.V16.0)

## 📉 PCA & Scree Plot
We reduced dimensionality using PCA:
- **PC1** captured household structure (e.g., family size, multigenerational households)
- **PC2** reflected socioeconomic differences (e.g., age and income)

**Scree Plot:** The first two PCs explained a significant portion of the variance, enabling effective visualization and clustering.

## 👥 Clustering Results

### 🔹 K-Means Clustering (k=3)
Using Elbow and Silhouette methods, we selected `k=3`:
- **Cluster A**: Large families, multigenerational households
- **Cluster B**: Young renters, lower income (likely students)
- **Cluster C**: Older, wealthier individuals in smaller households

### 🔸 Hierarchical Clustering
Tried all four linkage methods (single, complete, average, ward).
- Best results via **average linkage**, but clusters were unbalanced
- **K-Means** proved more interpretable and stable for this dataset

## 🧩 Matrix Completion
We tested PCA-based imputation:
- Simulated missing data and iteratively reconstructed using **top 5 PCs**
- Converged in 6 iterations
- Final correlation between imputed and true values: **0.61**

## 📈 Visuals
The notebook includes:
- Scree Plot
- PCA Scatter Plot
- K-Means Cluster Plots
- Hierarchical Dendrograms
- Matrix Completion Error Convergence

## 📌 Key Takeaways
- PCA effectively reduced complexity while retaining interpretability
- K-Means clustering revealed **three distinct renter segments**
- Matrix Completion is a viable tool to handle missing census data
- These techniques could inform **housing policy and urban planning**

## 🧠 Authors
- Doung Le
- Eloho Okoloko
- Surya Kailash Ramesh

## 📎 Blog Post
[📖 Read the full blog post](https://github.com/Eliokay/Practical-Homework-4/blob/main/Unsupervised%20learning%20blog%20post.pdf))

## 📂 Folder Contents
- `Unsupervised_Learning.ipynb`: Main notebook with all analysis
- `README.md`: Project overview and documentation
- `Unsupervised learning blog post.pdf`: Final write-up for the assignment

---

**Note:** All analysis was performed using Python libraries such as `scikit-learn`, `matplotlib`, `seaborn`, and `numpy`.
