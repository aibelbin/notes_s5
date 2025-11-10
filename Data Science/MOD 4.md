## Clustering 

Clustering is the process of partitioning a dataset to subsets in a way that the data present in one subset is only similar to the ones in the same and different to data present in other subsets or clusters 

Clustering is unsupervised as labels arent provided, the quality of the clustering depends on the algorithm and the distance functions it applies 

The set of clusters resulting from a cluster analysis is called a clustering 
The quality of the cluster depends on the algorithm, distance function and the application 


## K means algorithm 

In K means algorithms, the cluster centre is represented as the mean of all the objects in the cluster 

### Steps 


## K medaloids algorithm 

This is similar to k means but instead of choosing the mean as the centroid of the cluster, datapoint is choosen as the centroid


### Steps 

## Hierarchical clustering 

Partition data objects into groups at different levels 

### Agglomerative clustering 

It uses bottom up strategy, it starts off by considering each object as a singular cluster and then these clusteres finds clusters that are similar to each other and then these are merged together into large groups until certain breaking condition is met 


### Divisive clustering 

Here the clustering is based on a bottom down strategy, here all the objects are considered to be a singular cluster and then divide them with each iteration into smaller sub clusters, this continues until each cluster contains one object or any other condition is satisfied 


**Dendogram** Is a tree like structure used to represent the hierarchical structure. 

If an algorithm uses minimum distance it is called nearest neighbor clustering algorithm however if it uses maximum distance, its called farthest neighbor clustering algorithm


## Association Rule Mining 

It is an unsupervised learning technique used to learn the shopping behavior or business behavior

The rules that support both minimum support threshold and minimum confidence threshold are called strong association rules 

