In machine learning , we split the data we have to training and testing data (validation dataset) but having a singular validation set is not enough to measure the difference/performance of ai models hence it has to be done by multiple validation sets like k fold or cross validation 

For every learning algorithm theres a dataset that gives the best accuracy and also a dataset which performance is poor, this is called **No free Lunch theorem**

## Cross validation 

Cross validation is a technique where we split the original dataset to training set to train the model and testing dataset to test the data 

**Holdout method** is the simplest form of cross validation the data is split into two and the function fits the data and the function is used to predict the values from the model and this is cross verified with the test data 

## K fold cross validation 

In k fold cross validation, the dataset is split into k folds, or k sets and k of the data is used for testing and k-1 is kept for training 

## Bootstrapping 

Bootstrapping means random sampling with replacement, this randomly selection samples and these are selected with replacement which is called as bootstrapping, and this is used to train and validate the model 

## Confusion Matrix

Confusion matrix is table drawn from a dataset where true values are known, it is used to evaluate the performance of  model 