# Clustering – Study Notes

## What is Clustering
- Clustering is an unsupervised learning technique used to group data points into clusters based on similarity.  
- Unlike supervised learning, clustering works without labelled data — it finds natural structures and patterns in the dataset.

---

## Goals of Clustering
- Identify groups or patterns within data.  
- Discover similarities or differences among data points.  
- Summarise large datasets by representing them with fewer cluster centroids.  
- Support exploratory data analysis, anomaly detection, or segmentation tasks.

---

## Common Clustering Algorithms

### 1. K-Means Clustering
- Most widely used algorithm for clustering numeric data.  
- Objective: Minimise the sum of squared distances (SSE) between each data point and its assigned cluster centroid.  
- Requires the user to specify k (the number of clusters).  

**Steps:**
1. Choose k cluster centroids randomly.  
2. Assign each data point to the nearest centroid.  
3. Update centroids as the mean of points in each cluster.  
4. Repeat steps 2–3 until centroids stabilise.

**Pros:** Simple, efficient, and scalable.  
**Cons:** Sensitive to outliers, requires predefined k, assumes spherical clusters.

---

### 2. Hierarchical Clustering
- Builds a hierarchy of clusters (tree-like structure called a dendrogram).  
- Two main approaches:  
  - Agglomerative: Bottom-up — each data point starts as its own cluster, then merges progressively.  
  - Divisive: Top-down — all points start in one cluster, then split recursively.  
- No need to predefine the number of clusters.

**Pros:** Visual interpretation using dendrograms.  
**Cons:** Computationally expensive on large datasets.

---

### 3. DBSCAN (Density-Based Spatial Clustering of Applications with Noise)
- Groups points that are densely packed and separates outliers.  
- Does not require the number of clusters in advance.  
- Works with parameters:
  - eps (radius of neighbourhood)
  - min_samples (minimum points to form a cluster)

**Pros:** Handles noise and irregular cluster shapes.  
**Cons:** Performance depends on parameter selection.

---

### 4. Gaussian Mixture Models (GMM)
- A probabilistic model assuming data is generated from a mixture of several Gaussian distributions.  
- Uses the Expectation-Maximization (EM) algorithm to estimate cluster parameters.  
- Each point belongs to a cluster with a probability, not an absolute assignment.

**Pros:** Soft clustering (probabilistic membership).  
**Cons:** Sensitive to initialisation and assumes Gaussian-shaped clusters.

---

## Evaluating Clustering Performance

Since clustering is unsupervised, we usually assess internal validity — how well clusters fit the data.

### 1. Silhouette Score
- Measures how similar a point is to its own cluster compared to others.  
- Range: -1 (poor fit) to +1 (well-clustered).  
- Average silhouette score across data indicates cluster quality.

### 2. Sum of Squared Errors (SSE)
- Used in K-Means to measure compactness of clusters.  
- Lower SSE = tighter clusters, but too low may mean overfitting.  
- Elbow Method: Plot SSE vs. k to choose the best number of clusters.

### 3. Davies–Bouldin Index
- Lower values indicate better separation between clusters.

---

## Example in Scikit-Learn

```python
from sklearn.cluster import KMeans
from sklearn.metrics import silhouette_score
import pandas as pd

# Load data
df = pd.read_csv("data.csv")

# Choose number of clusters
k = 3

# Create model
kmeans = KMeans(n_clusters=k, random_state=42)
kmeans.fit(df)

# Get labels and evaluate
labels = kmeans.labels_
score = silhouette_score(df, labels)

print("Cluster centres:\n", kmeans.cluster_centers_)
print("Silhouette Score:", score)
```

---

## Applications of Clustering
- Customer segmentation (marketing, retail).  
- Anomaly detection (fraud, network intrusion).  
- Document or image grouping.  
- Gene expression analysis in bioinformatics.  
- Recommendation systems and topic modelling.

---

## Advantages
- Uncovers hidden structures in data.  
- Works without labels.  
- Helps reduce data dimensionality.  

## Limitations
- Number of clusters can be subjective.  
- Sensitive to scale and noise.  
- Different algorithms can produce different results.  

---

## Best Practices
- Always scale data (standardise features) before clustering.  
- Use Elbow or Silhouette methods to find the optimal number of clusters.  
- Visualise results using scatter plots, PCA, or t-SNE.  
- Compare multiple algorithms for robustness.
