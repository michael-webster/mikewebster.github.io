This chapter shows examples of how to create segments of a customer base using a few different types of clustering algorithms including k-means and k-medians clustering.

## The goal

Marketers want to target specific groups of customers with messages that appeal to them, the more appealing the message (hopefully) the more likely you are to buy. One way of creating these `segments` of your customer base is using `k-means` clustering.

## What is k-means

[K-means clustering](https://en.wikipedia.org/wiki/K-means_clustering) is an *unsupervised* machine learning technique used to create clusters from observed data. First, you pick how many clusters you want then the algorithm assigns your data to a cluster based on the best fit. Here, best fist means the smallest average distance between a data point and the center of it's cluster. Some *optimization* algorithm moves the centers around until it finds one that minimizes the average distance.  K-means can't tell us what the clusters mean, but it can find them.
