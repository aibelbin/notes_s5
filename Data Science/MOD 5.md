In machine learning , we split the data we have to training and testing data (validation dataset) but having a singular validation set is not enough to measure the difference/performance of ai models hence it has to be done by multiple validation sets like k fold or cross validation 

For every learning algorithm theres a dataset that gives the best accuracy and also a dataset which performance is poor, this is called **No free Lunch theorem**

---
# Data Based 
## Cross validation 

Cross validation is a technique where we split the original dataset to training set to train the model and testing dataset to test the data 

**Holdout method** is the simplest form of cross validation the data is split into two and the function fits the data and the function is used to predict the values from the model and this is cross verified with the test data 

## K fold cross validation 

In k fold cross validation, the dataset is split into k folds, or k sets and k of the data is used for testing and k-1 is kept for training 

## Bootstrapping 

Bootstrapping means random sampling with replacement, this randomly selection samples and these are selected with replacement which is called as bootstrapping, and this is used to train and validate the model 

# Metric Based 

## Confusion Matrix

Confusion matrix is table drawn from a dataset where true values are known, it is used to evaluate the performance of  model 

| **Actual / Predicted** | **Predicted Positive** | **Predicted Negative** |
| ---------------------- | ---------------------- | ---------------------- |
| **Actual Positive**    | True Positive (TP)     | False Negative (FN)    |
| **Actual Negative**    | False Positive (FP)    | True Negative (TN)     |

**Explanation:**
- **TP (True Positive):** Model correctly predicts the positive class.  
- **TN (True Negative):** Model correctly predicts the negative class.  
- **FP (False Positive):** Model incorrectly predicts positive (Type I error).  
- **FN (False Negative):** Model incorrectly predicts negative (Type II error).

**1️ Accuracy**

Measures the overall correctness of the model.

$$
Accuracy = \frac{TP + TN}{TP + TN + FP + FN}
$$

---

**2️ Precision (Positive Predictive Value)**

Indicates how many predicted positives are actually positive.

$$
Precision = \frac{TP}{TP + FP}
$$

---

**3️ Recall (Sensitivity or True Positive Rate)**

Indicates how many actual positives are correctly predicted.

$$
Recall = \frac{TP}{TP + FN}
$$

---

**4️ F1-Score**

Harmonic mean of Precision and Recall — balances both metrics.

$$
F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}
$$

---

**5️Specificity (True Negative Rate)**

Indicates how many actual negatives are correctly predicted.

$$
Specificity = \frac{TN}{TN + FP}
$$

---

**6️Error Rate**

Measures the proportion of incorrect predictions.

$$
Error\ Rate = \frac{FP + FN}{TP + TN + FP + FN}
$$ 
---
## Ensemble learning 

The type of machine learning where multiple weak models are put together to get a perfomative model is known as ensemble learning 

### Multiclass classification problem 

Let there be n class labels C1 , C2 , . . . , Cn . Let x be a test instance and let there be L base
learners. Here also, each of the base learners will assign a class label to x and when a class
label is assigned a label, the label gets a vote. In the voting scheme, the class label which gets
the maximum number of votes is assigned to x.


### Regression 

#### Voting 
Combine the prediction from multiple models 

#### Bagging 

This is the type of model training where the model is trained on different samples of the same dataset, this is using bootstrapping, different subsets of the same dataset

#### Boosting 

this is the type of learning where the new model focuses on the errors of the previous model and focussing on correcting the previous errors 

#### Random forest 

A group of decision trees are put together and their outputs are put together to get a final output, this is how random forest works The subset for each decision tree is by creating samples of data with replacement. (bootstrapping)


1. **Bootstrap Sampling:**
   - Create multiple subsets of the original dataset by random sampling *with replacement*.
   - Each subset will be used to train one Decision Tree.

2. **Build Decision Trees:**
   - For each subset, build a Decision Tree.
   - At every split, consider only a random subset of features instead of all features.
   - This reduces correlation between trees hence thereby introducing feature randomness

3. **Aggregate Predictions:**
   - After training, each tree makes its own prediction.
   - For classification → take a **majority vote**.
   - For regression → take the **average** of all tree outputs.

4. **Final Output:**
   - Combine all predictions to get the final, more accurate and stable result.

---
## Improving model perfomance 

•Clean and preprocess data: Address missing values, outliers,
and inconsistencies. Standardize and normalize data to ensure it's
in a suitable format for the model.

•Add more data: Increasing the volume and diversity of your
training data can help the model learn more patterns and
generalize better.

•Feature engineering: Create new, more informative features
from existing data. This can include combining, transforming, or
creating new variables to help the model make better predictions.

•Feature selection: Identify and remove irrelevant or redundant
features to reduce noise and complexity. Domain knowledge and
statistical metrics can help in this process.

Model-centric improvements

•Choose the right model: Select a model that is appropriate for
your specific data and problem. A linear model may not work well
for highly non-linear data, for example.

•Hyperparameter tuning: Adjust the model's parameters (like
the number of hidden layers in a neural network or the number of
neighbors in KNN) to optimize its performance.

•Regularization: Apply techniques to prevent overfitting, which
occurs when a model becomes too complex and performs poorly
on new data. Regularization adds a penalty to model complexity.•

Ensemble methods: Combine the predictions of multiple models
to improve accuracy. Techniques include bagging (e.g., Rand