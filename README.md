
# KMeans Clustering

## Introduction

KMeans is an algorithm for clustering data into homogeneous groups. Clustering algorithms are a category of unsupervised learning algorithms. While classification algorithms attempt to predict an attribute or category that we have seen or labelled previously, the groupings provided by clustering algorithms are not predefined.  
  
KMeans itself works as follows: first, a number of desired clusters is selected. From there, starting points, one for each cluster, are selected. This choice of starting points affects the results of the algorithm and is therefore a critical choice. In practice, a heuristic strategy is often used to determine initial points, or the algorithm is run multiple times with different starting points and the results compared. In the upcoming lab, you'll get a chance to experiment and preview this in practice. Once starting points is selected, the distance from each of these points to each of the observation points is calculated, and each row of data is assigned to the closest starting point. Once each row has been assigned to a cluster, the center of these clusters is calculated. From there, the process is repeated. The distance between every row of data and each of these cluster centers is calculated, and rows are reassigned to the cluster they are closest to. In practice, most points are likely to remain in the same cluster, while some jump from one group to the next. This process continues until a maximum number of iterations is met, or no points change cluster assignment, at which point the algorithm has converged. Again, it is important to remember that the initialization points chosen have a substantial impact on the resulting clusters.

## Determining K

Another important consideration in the KMeans algorithm is determining an optimal number of clusters. In many applications such as segementing a business audience, there may be specific business needs which impact the choice of K. For example, it may only be practical to produce 3-5 customer segments, as a business team might not have ample resources to produce customization to more then 5 audiences. There is also not good method for choosing an optimal number of clusters before running the algorithm. Instead, the algorithm is typically run multiple times, with different numbers of clusters and the results are compared. One common measurement for comparing these results is **inertia**. Inertia is the sum of the distances of all points from their cluster centers. Interestingly, the inertia will always decrease as the number of clusters increases. For example, imagine the extreme example where the number of clusters is the same as the number of starting points; each of the points will form its own cluster, and as a result, the distance from each point to its cluster center will be zero (there is no distance between a point and itself). So while the inertia will always decrease, we often look for an 'elbow' in the curve, beyond which the inertia does not rapidly decrease as the number of clusters continues to increase.

<img src="kmeans_elbow.png" width=800>

Notice that after the elbow, the distance from points to cluster centroids continues to decrease but at a marginal rate.

## Additional Resources

Take a look at some additional resources from SciKitLearn and Oracle for further information.  

http://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html
http://scikit-learn.org/stable/modules/clustering.html

https://www.datascience.com/blog/k-means-clustering
