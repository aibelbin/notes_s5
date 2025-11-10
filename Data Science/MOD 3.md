

## Classification 

It is the process of categorising inputs or datapoints to pre determined classes, output type is discrete

## Regression

It is the process of predicting continuous numerical values, Estimate a real value quantity

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

In naive bayes we can predict the class membership probabilities such that  the probability tht a given item belongs to a particular class 

It runs on the following assumptions 
1.  all features are independent and unrelated to each other presence or absence of a feature does not affect the presence or absence of another feature 
2.  Class conditional independence ie, If a class is known, knowing one feature wont give the ability to find another feature 


## Bayesian Belief Network 

It is a probabilistic graphical model that represents conditional dependencies between random variables. they assume that, given a class label the value of the attributes are conditionally independent
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

## Back Propogation 
#### Training Algorithm Steps

---

**Step 1:**  
Initialize weights and learning rates.

---

**Step 2:**  
Calculate net input to each hidden unit \( z_j \) using:

$$
Z_{inj} = Z_{0j} + \sum_{i=1}^{n} x_i V_{ij}
$$

---

**Step 3:**  
Calculate output from hidden layer by applying activation function over \( Z_{inj} \):

$$
Z_j = f(Z_{inj})
$$

---

**Step 4:**  
For each output unit \( y_k \), \( k = 1, 2, \ldots, m \):

$$
Y_{ink} = W_{0k} + \sum_{j=1}^{l} z_j W_{jk}
$$

---

**Step 5:**  
Apply activation function to compute output signal:

$$
Y_k = f(Y_{ink})
$$

---

**Step 6:**  
For each output unit \( y_k \), compute the error correction using the formula:

### For output layers:
$$
\delta_k = f'(Y_{ink}) (t_k - y_k)
$$

or equivalently,

$$
\delta_k = f(Y_{ink}) (1 - f(Y_{ink})) (t_k - y_k)
$$

### For hidden layers:
$$
\delta_j = f(Z_{inj}) (1 - f(Z_{inj})) \sum_k \delta_k W_{jk}
$$


once the output is calculated, it is checked and back progration is done to correct the weights


Back propagation is the **essence of neural network training**.  
It is the method of **fine-tuning the weights** of a neural network based on the **error obtained in the previous epoch**.

Proper tuning of the weights allows the model to:
- Reduce error rates,
- Make the model more reliable,
- And increase its generalization.

The algorithm is used to effectively train a neural network through a method called **"chain rule"**.  
In simple terms, after each forward pass through the network, back propagation performs a **backward pass** in which the model parameters (weights and biases) are **adjusted**.

---

### Steps
 
Initially, the **weights are assigned at random**.  
Then the algorithm iterates through many cycles of two processes until a stopping criterion is reached.  
Each cycle is known as an **epoch**.

Each **epoch** includes:

---

###  1. Forward Phase

In this phase, the **input for the training instances** are fed into the neural network.  
This results in a **forward cascade of computations** across the layers using the current set of weights.

The final predicted output can then be compared to the **target output** of the training instance, and the **derivative of the loss function** with respect to the output is computed.

---

###  2. Backward Phase (Backpropagation Step)

The errors from the output layer are **propagated backward** through the network to adjust the weights.

Each neuron’s weight update depends on:
- The derivative of the loss function,
- The neuron’s activation output,
- And the learning rate.

The goal is to minimize the **overall loss (error)** by updating weights in the direction of steepest descent (negative gradient).

---

###  3. Weight Update Rule

Weights are updated using the **gradient descent rule**:

$$
W_{ij}(t+1) = W_{ij}(t) + \eta \, \delta_j \, x_i
$$

where:
- \( \eta \) = learning rate  
- \( \delta_j \) = error term for neuron \( j \)  
- \( x_i \) = input to neuron \( j \)

---

###  4. Epoch and Convergence

This **forward–backward cycle** is repeated for multiple epochs until:
- The total error is below a threshold, or  
- A maximum number of epochs is reached.

At convergence, the network’s weights are optimized to produce minimal output error on the training data.

---

### Summary

| Term                  | Meaning                                             |
| --------------------- | --------------------------------------------------- |
| **Epoch**             | One complete pass of forward + backward propagation |
| **Forward Phase**     | Compute output using current weights                |
| **Backward Phase**    | Compute error and update weights                    |
| **Learning Rate (η)** | Controls how fast the weights are updated           |
| **Loss Function**     | Measures error between predicted and actual outputs |

---
