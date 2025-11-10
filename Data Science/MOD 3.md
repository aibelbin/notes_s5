
## Decision Trees 

Decision tree is a type of supervised learning algorithm used for classification and regression type of problem to take decision based on mapped out possibilities and their outcomes 
Its a tree like structure and contains different leaves and nodes, the top most node is known as root node which contains the most significant feature, represents the entire dataset from there the nodes split differently based on features 

**Feature selection methods** decide which node has to be the root node at each level of the decision tree, this method of selection increases the accuracy and performance of the tree
	Information gain 
	Gini Index 

**Entropy**
It is the measure of impurity in the dataset, entropy values can range from 0 to 1 

#### Pruning 
Pruning can be done on trees to reduce overfitting, pruning is the process of removing branches of the tree that has very less predictive power.
### Working of the decision tree 

- Start at the **root node** (whole dataset).
    
- Evaluate all features and choose the one that gives the **best split** (based on a criterion like _Information Gain_ or _Gini Index_).
    
- Split the dataset into subsets based on that feature.
    
- Repeat the process recursively for each subset until:
    
    - All samples in a node belong to one class, or
        
    - No more features remain, or
        
    - A stopping criterion (like max depth) is met.

**Root node** is selected based on the feature that gives the best split 

**Information gain** is the measure of reduction in entropy achieved by splitting a specific feature 


## Naive Bayers  Algorithm 

The naive bayers algorithm is based on the following assumptions 

1.  all features are independent and unrelated to each other presence or absence of a feature does not affect the presence or absence of another feature 
2. The data has class conditional independence, the  events are independent as long as they are conditioned on the same class 



## Types of learners 

### Lazy learners (Instance based learners)

These are the type of models which do not prepare or generalize the model when training set is given, instead when a inference or input is given for prediction or classification, it goes thru the dataset to generate the output

Take less time in training as they dont generalize, waits for the test instance hence also known as instance based learners 

They support incremental learning, needs more storage to store their data 

eg :- K nearest neighbor 

### Eager Learners 

Eager learners, when given a set of training tuples, will
construct a generalization (i.e., classification) model before receiving new (e.g., test)
tuples to classify.

## K nearest neighbor 

This is the type of algorithm which compares the test data with the training data and tries to find the point in the training data that is closest to the test data, this is how knn algorithm works, 
closesness is measured in measure of euclidean distance 


the **partial distance method**, we compute
the distance based on a subset of the n attributes. If this distance exceeds a threshold,
then further computation for the given stored tuple is halted, and the process moves on
to the next stored tuple


## Case based reasoning 

`basically rag system`

In case base reasoning unlike the knn the training data is not measure with points but the training data is stored as cases as tuples, when a similar case occurs the training data is gone thru, a case based reasoner will first check and identify  if the training data exists, if it does, an accompanying
solution to the case is sent back. Challenges of case based reasoning include not having a similarity metrics to measure the similarity between the inference test data and the training data. 

Sometimes additional knowledge base can also be attached to the case based reasoning model for better solutions, used in business eg. customer service 

## Support Vector Machine (SVM)

Its an algorithm for the classification for linear and non linear data, in this method, the training data is mapped to a higher dimension and using this dimension a linearly optimal hyperplane is found which can separate one class from another, the svm finds the hyperplane by using **support vector** and **margin**. 

**Margin** is the distance between the hyperplane and the closest point from each class 

**Support vectors** are the closest lying data points from the hyperplane 

Sometimes the data isnt always linearly separable, in this case kernels are used to map them to linearly separable data to map them to a higher dimension 