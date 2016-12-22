This chapter shows examples of how to create segments of a customer base using a
few different types of clustering algorithms including k-means and k-medians
clustering.

## The goal

Marketers want to target specific groups of customers with messages that appeal
to them, the more appealing the message (hopefully) the more likely you are to
buy. One way of creating these `segments` of your customer base is using
`k-means` clustering.

## What is k-means

[K-means clustering](https://en.wikipedia.org/wiki/K-means_clustering) is an
*unsupervised* machine learning technique used to create clusters from observed
data. First, you pick how many clusters you want then the algorithm assigns your
data to a cluster based on the best fit. Here, best fist means the smallest
average distance between a data point and the center of it's cluster. Some
*optimization* algorithm moves the centers around until it finds one that
minimizes the average distance.

K-means can't tell us what the clusters mean, but it can find them.

## Finding the right K
You have to decide the number of clusters when you start, but you need a way to
know if you picked the right number. The *silhouette* gives you a way of
assessing how good K is. The silhouette ranges from -1 to 1, the bigger the
number the better the fit of k.

To calculate the silhouette: subtract the average
distance of a point from the points in the closest neighboring cluster and the
average distance of a point from the points in it's assigned cluster, and then
divide by the larger of the two.

## Problems with k-means
K-means has a few issues:

* It struggles with sparse data
* You can get "weird" clusters that are hard to explain

## K-medians
[K-medians clustering](https://en.wikipedia.org/wiki/K-medians_clustering) is an tweak on k-means. We still try to pick K clusters, but you use median distance instead of mean. The book describes it as only using the 1's from a vector in the data set.

When you use k-medians, the euclidean distance metric from k-means doesn't work as well because it's non-linear. An alternative is to use *cosine* distance, an asymmetric distance metric. Cosine also works well since a purchase is more informative than a non-purchase, people have lots of reasons *not* to buy so a non-purchase doesn't tell us much. With cosine similarity we get to cluster on similarity, and not just differences.

## Chapter 2 Summary

- K-means clusters data points together to minimize average ditances from a center point
- The value for K is picked ahead of time
- Use an optimization algorithm to find the minimum distance
- K-means has some issues on sparse data
- K-medians and an asymmetric distance function can provide better clustering in the sparse case
- Some data may need to be normalized before using the clustering algorithm, "center" and "scale"
- Use clustering when you want to divide customers into groups to better understand/market to them
