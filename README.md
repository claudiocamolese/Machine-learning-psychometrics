# Machine Learning for Behavioral and Personality Analysis using PCA

This repository explores the use of **Principal Component Analysis (PCA)** to identify and analyze patterns in human **habits**, **preferences**, and **behavioral tendencies**. The goal is to uncover hidden structures and correlations between people's daily habits and their personality traits through dimensionality reduction and visualization techniques.

---

## 📌 Project Overview

In many real-world datasets, especially those involving **survey responses** or **behavioral tracking**, we face high-dimensional data. Each person may be described by dozens (or hundreds) of features — from music preferences to sleep patterns or social behavior. Understanding the underlying structure of such data can be challenging.

In this project, we apply **PCA** to:

- Reduce the dimensionality of complex personal behavior datasets.
- Discover which combinations of behaviors are most informative.
- Visualize latent personality components.
- Gain insight into how different habits correlate with one another and with potential personality clusters.

---

## 🧠 What is PCA?

**Principal Component Analysis (PCA)** is a linear technique for dimensionality reduction. It transforms a dataset of possibly correlated variables into a set of linearly uncorrelated variables called **principal components**.

### 🧮 Mathematical Explanation

Let $X \in \mathbb{R}^{n \times d}$ be the data matrix, where:
- $n$ is the number of samples (individuals),
- $d$ is the number of features (habits/preferences).

1. **Center the Data**:  
   PCA starts by centering the data by subtracting the mean of each column from the respective values:

   $$\tilde{X} = X - \mu$$

   where $\mu$ is the mean vector of $X$, with each element being the average of the corresponding column in $X$.

2. **Covariance Matrix**:  
   The next step is to compute the **covariance matrix** to understand how the features (columns) of $X$ vary with respect to each other:

   $$C = \frac{1}{n-1} \tilde{X}^T \tilde{X}$$

   where $C$ is the $d \times d$ covariance matrix. The covariance matrix captures the relationships between all pairs of features.

3. **Eigenvalue Decomposition**:  
   To find the directions of maximum variance (the principal components), we compute the **eigenvalues** and **eigenvectors** of the covariance matrix $C$:

   $$C v_i = \lambda_i v_i$$

   where:
   - $v_i$ is the eigenvector corresponding to the $i$-th principal component, which is the direction in feature space that explains the most variance.
   - $\lambda_i$ is the eigenvalue associated with $v_i$, which represents the amount of variance explained by that principal component.

4. **Principal Components**:  
   Once we have the eigenvectors and eigenvalues, the eigenvectors are sorted in decreasing order of their eigenvalues. These top eigenvectors represent the **principal components**. The original data $X$ is projected onto these components:

   $$Z = \tilde{X} V_k$$

   where $V_k$ is the matrix of the top $k$ eigenvectors (principal components), and $Z$ is the projection of the data into a lower-dimensional space of $k$ dimensions.

5. **Interpretation**:  
   Each principal component is a linear combination of the original features, and it explains a portion of the total variance in the dataset. By retaining the first few components, we can capture most of the variation in the data while discarding the less important components.

