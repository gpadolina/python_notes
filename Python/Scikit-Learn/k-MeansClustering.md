Clustering algorithms are unsupervised machine learning models that seek to learn an optimal division or discrete labeling of groups of
points from the properties of the data. The basis of k-means model are:
  1. The "cluster centroid" is the arithmetic mean of the all the points belonging to the cluster.
  2. Each point is closer to its own centroid than to other cluster centroids.
```
from sklearn.cluster import KMeans
kmeans = KMeans(n_cluster=2) # You may not know the right number of clusters to use at first.
kmeans.fit(X)
y_kmeans = kmeans.predict(X)
```

## Expectation-Maximization
  1. Get some cluster centers
  2. Repeat until converged
     a. *E-Step*: assign points to the nearest cluster center
     b. *M-Step*: set the cluster centers to the mean
     
Under typical circumstances, each repetition of the E-step and M-step will always result in a better estimate of the cluster characteristics.

#### Limitations
1. The globally optimal result may not be achieved
2. The number of clusters must be selected beforehand
3. k-means is limited to linear cluster boundaries
4. k-means can be slow for large numbers of samples

### Kernelized k-means
```
from sklearn.cluster import SpectralClustering
model = SpectralClustering()
label = model.fit_predict(X)
```
While simple and easy to understand, the nonprobabilistic nature of k-means and its use of simple distance-from-cluster-center to assign cluster membership leads to poor performance for many real-world situations.
