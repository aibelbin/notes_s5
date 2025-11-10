
## Decision Trees 

Decision tree is a type of supervised learning algorithm used for classification and regression type of problem to take decision based on mapped out possibilities and their outcomes 
Its a tree like structure and contains different leaves and nodes, the top most node is known as root node which contains the most significant feature, represents the entire dataset from there the nodes split differently based on features 

**Feature selection methods** decide which node has to be the root node at each level of the decision tree, this method of selection increases the accuracy and performance of the tree
	Information gain 
	Gini Index 

**Entropy**
It is the measure of impurity in the dataset, entropy values can range from 0 to 1 

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