## Clustering 

Clustering is the process of partitioning a dataset to subsets in a way that the data present in one subset is only similar to the ones in the same and different to data present in other subsets or clusters 

Clustering is unsupervised as labels arent provided, the quality of the clustering depends on the algorithm and the distance functions it applies 

The set of clusters resulting from a cluster analysis is called a clustering 
The quality of the cluster depends on the algorithm, distance function and the application 


## Partition Clustering

### K means algorithm 

In K means algorithms, the cluster centre is represented as the mean of all the objects in the cluster 

#### Algorithm 

1. **Input:**  
   - Number of clusters, `k`
   - Dataset, `D = {x₁, x₂, ..., xₙ}`

2. **Initialize:**  
   Randomly select `k` points from the dataset as **initial centroids**.

3. **Assignment Step:**  
   For each data point `xᵢ`, assign it to the cluster whose centroid is closest:
   $$
   C_j = \{ xᵢ : ||xᵢ - μ_j||^2 \le ||xᵢ - μ_l||^2 \; \forall l, 1 \le l \le k \}
   $$

4. **Update Step:**  
   Recalculate the centroid (mean) of each cluster:
   $$
   μ_j = \frac{1}{|C_j|} \sum_{xᵢ \in C_j} xᵢ
   $$

5. **Repeat:**  
   Continue **Assignment** and **Update** steps until:
   - Centroids do not change, or
   - The change is below a threshold.

6. **Output:**  
   - Final cluster centroids  
   - Clustered dataset


### K medaloids algorithm 

This is similar to k means but instead of choosing the mean as the centroid of the cluster, datapoint is choosen as the centroid

#### Algorithm 


1. **Input:**  
   - Number of clusters, `k`  
   - Dataset, `D = {x₁, x₂, ..., xₙ}`

2. **Initialize:**  
   Randomly select `k` data points as the **initial medoids**.

3. **Assignment Step:**  
   Assign each data point to the cluster with the **nearest medoid**:
   $$
   C_j = \{ xᵢ : d(xᵢ, m_j) \le d(xᵢ, m_l) \; \forall l, 1 \le l \le k \}
   $$

4. **Update Step:**  
   For each cluster, choose the point that minimizes the total distance to all other points in the cluster as the **new medoid**:
   $$
   m_j = \arg \min_{x_p \in C_j} \sum_{x_q \in C_j} d(x_p, x_q)
   $$

5. **Repeat:**  
   - Reassign points to nearest medoids
   - Recalculate medoids  
   Until there is **no change** in medoids.

6. **Output:**  
   - Final set of medoids  
   - Clustered dataset


## Hierarchical clustering 

Partition data objects into groups at different levels 

### Agglomerative clustering 

It uses bottom up strategy, it starts off by considering each object as a singular cluster and then these clusteres finds clusters that are similar to each other and then these are merged together into large groups until certain breaking condition is met 


### Divisive clustering 

Here the clustering is based on a bottom down strategy, here all the objects are considered to be a singular cluster and then divide them with each iteration into smaller sub clusters, this continues until each cluster contains one object or any other condition is satisfied 


**Dendogram** Is a tree like structure used to represent the hierarchical structure. 

If an algorithm uses minimum distance it is called nearest neighbor clustering algorithm however if it uses maximum distance, its called farthest neighbor clustering algorithm

## DB Scan (Density based clustering)

Density based clustering is to create clusters based on the density or population of similar points in an area. 

In density based clustering the algoritm takes two values $\epsilon$ and MinPts,

Here $\epsilon$ = Radius of points around the selected point and
MinPts = Number of points required to form a cluster 

#### Algorithm works as follow :- 
1. Start by selection an unselected point and take $\epsilon$ and Minpts values 
2. Check the surrounding of the selected point within the $\epsilon$ 
3. If the number of points around the point is > Minpts ; Point becomes a cluster and if the MinPts is > No of points, the points are marked as outlier (temporarily)
4. This process continues until some threshold value is hit or all points are gone through 
## Association Rule Mining 

It is an unsupervised learning technique used to learn the shopping behavior or business behavior

The rules that support both minimum support threshold and minimum confidence threshold are called strong association rules 

### Apriori Algorithm 

Apriori algorithm is used to find frequent datasets and to create or find assosiation rules between them in large transactional database, mainly used for market basket analysis 
“If a customer buys _bread_ and _butter_, they are likely to buy _jam_ too.”


Support and Confidence 

**Support** indicates how frequently an option appears in the dataset
 $$
\text{Support}(A \Rightarrow B) = \frac{\text{Number of transactions containing both A and B}}{\text{Total number of transactions}}
$$


**Confidence** is a measure of how frequently the rule has found to be true 


$$
\text{Confidence}(A \Rightarrow B) = \frac{\text{Support}(A \cup B)}{\text{Support}(A)} = P(B|A)
$$

#### Algorithm 

1. Identifying Frequent Item-Sets

•The Apriori algorithm starts by looking through all the data to count how
many times each single item appears. These single items are called 1-Item-
Sets.
•Next it uses a rule called minimum support this is a number that tells us
how often an item or group of items needs to appear to be important. If an
item appears often enough meaning its count is above this minimum
support it is called a frequent Item-Set.

2. Creating Possible Item Group

•After finding the single items that appear often enough (frequent 1-item
groups) the algorithm combines them to create pairs of items (2-item
groups). Then it checks which pairs are frequent by seeing if they appear
enough times in the data.
•This process keeps going step by step making groups of 3 items, then 4
items and so on. The algorithm stops when it can’t find any bigger groups
that happen often enough.

3. Removing Infrequent Item Groups

•The Apriori algorithm uses a helpful rule to save time. This rule says: if a
group of items does not appear often enough then any larger group that
includes these items will also not appear often.
•Because of this, the algorithm does not check those larger groups. This way
it avoids wasting time looking at groups that won’t be important make the
whole process faster.4. Generating Association Rules

The algorithm makes rules to show how items are related.

### Corealation analysis 

Correlation analysis is the study of strength and direction of linear relationship between two variables 