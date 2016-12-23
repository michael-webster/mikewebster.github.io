This chapter shows examples of how to create segments of a customer base using a
few different types of clustering algorithms including k-means and k-medians
clustering.

## The Goal

Marketers want to target specific groups of customers with messages that appeal
to them, the more appealing the message (hopefully) the more likely you are to
buy. One way of creating these *segments* of your customer base is to use a clustering algorithm.

## K-means Clustering

[K-means clustering](https://en.wikipedia.org/wiki/K-means_clustering) is an
*unsupervised* machine learning technique used to create clusters from observed
data. First, you pick how many clusters you want then assign points to the cluster with the best fit.
Where "best" is the cluster with smallest average distance between a data point and
the center of it's cluster. An *optimization* algorithm moves the centers around until it finds the one that minimizes average distance.

**NOTE:** k-means can't tell us what the clusters mean, but it can find them.

## Finding the right k
With k-means, you need a way to tell if the value for k is a good one, the silhouette lets you do that.
The silhouette ranges from -1 to 1, the bigger the number the better the fit of k.

To calculate the silhouette: subtract the average
distance of a point from the points in the closest neighboring cluster and the
average distance of a point from the points in it's assigned cluster, and then
divide by the larger of the two.

## Problems with k-means
K-means has a few issues:

* It struggles with sparse data
* You can get "weird" clusters that are hard to explain

## K-medians
[K-medians clustering](https://en.wikipedia.org/wiki/K-medians_clustering) is similar to k-means. We still find k clusters, but you minimize the median distance from the center instead of the mean. The book describes it as only using the 1's from a vector in the data set.

When you use k-medians, the euclidean distance metric from k-means doesn't work as well because it's non-linear, instead we use *cosine distance*. Cosine distance is an *asymmetric* measure, this is useful for data sets like purchase information, where a lack of a purchase is not very informative since there are lots of reasons people don't purchase. The asymmetric distance metric with k-medians makes similarities in the data more important than differences when clustering.

## Chapter 2 Summary

- K-means clusters data points together to minimize average ditances from a center point
- The value for k is picked ahead of time
- Use an optimization algorithm to find the minimum distance
- K-means has some issues on sparse data
- K-medians and an asymmetric distance function can provide better clustering in the sparse case
- Some data may need to be normalized before using the clustering algorithm, "center" and "scale"
- Use clustering when you want to divide customers into groups to better understand/market to them
