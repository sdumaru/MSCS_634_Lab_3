# Lab 3: Clustering Analysis Using K-Means and K-Medoids

## Purpose  
This lab explores two clustering methods: K-Means and K-Medoids on the Wine dataset. After loading the data and applying z-score normalization to ensure all features contribute equally, I fit each algorithm with \(k=3\) to uncover natural groupings and evaluate how well they recover the known wine cultivars.

## Requirements  
- scikit-learn ≥ 1.2  
- scikit-learn-extra 0.3.0 (for `sklearn_extra.cluster.KMedoids`)  
```bash
pip install scikit-learn-extra
```

## Key Insights  
- **K-Means** achieved a Silhouette Score of 0.285 and an Adjusted Rand Index (ARI) of 0.897. The modest silhouette indicates some overlap at cluster boundaries, but the high ARI shows that K-Means correctly groups most samples according to their true labels.  
- **K-Medoids** yielded a Silhouette Score of 0.268 and an ARI of 0.741. The slightly lower silhouette and ARI suggest that, on this dataset, centroids capture class structure more accurately than actual-sample medoids, though the medoids provide robustness to outliers.  
- PCA visualizations confirmed that K-Means centroids sit centrally within clusters, while K-Medoids uses real data points that can appear near cluster edges.

## Challenges and Decisions  
- Using K-Medoids was challenging due to version mismatched . I had to install **scikit-learn-extra 0.3.0** for K-Medoids.
- I chose z-score normalization to place all features on a common scale for distance-based clustering.  
- I set \(k=3\) based on the known number of wine classes; optionally, an elbow or silhouette-vs-k plot could confirm this choice.  
- I applied PCA to reduce dimensionality to two components for clear, interpretable scatterplots.
