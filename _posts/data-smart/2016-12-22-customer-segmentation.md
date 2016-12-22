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
minimizes the average distance.  K-means can't tell us what the clusters mean,
but it can find them.

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
