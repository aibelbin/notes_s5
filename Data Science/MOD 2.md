
## Data Mining 

Data mining is discovering or mining knowledge from large set of data 

The data sources can include databases, data warehouses, the Web, and other
information repositories

Data mining turns  large collection of data into knowledge 


## Steps involved in knowledge discovery 

1. Data cleaning 
2. Data integration 
3. Data selection 
4. Data Transformation
5. Data Mining
6. Pattern Evaluation 
7. Knowledge presentation 


### Predictive models 

These models make predictions based on datasets it was trained on 

### Descriptive models 

These models learn the properties and hidden trends in the dataset 


### Classification 

Classification maps data  into predefined groups or classes 

### Regression 

Regression is used to map a data item to a
real valued prediction. Regression assumes that the
target data fit into some known type of function



## Clustering 

Clustering is grouping together similar data of the dataset but it is different from classification as clustering does not have any predefined classes meanwhile classification does  

### Sequence Discovery 

Sequential analysis or sequence discovery is used to
determine sequential patterns in data.


## Knowledge Discovery and Data mining 

Knowledge discovery in
databases (KDD) is the process of finding useful
information and patterns in data

Data mining is the use of
algorithms to extract the information and
patterns derived by the KDD process.


## Data Processing 

Data preprocessing is the process of transforming data into an more understandable format 


## Major tasks in Data Preprocessing 

1. Data cleaning 
2. Data Integration
3. Data reduction 
4. Data Transformation 
5. Data Discretization 


**Data cleaning**  is the process of removng incorrect data and inaccurate data  from the dataset 
**Noisy Data** is the data with large amount of useless information in them 



### Ways to tackle Noisy data 

1. Binning 
		Convert the dataset it equisized bins to perform median, boundary etc binning to smoothen the noisy data
2. Regression 
		This is done by fitting the data value to a function thereby reducing the variations that may cause noise, this helps to make the data smooth 
		this can be multiple or single linear function
3. Outlier analysis 
		Outliers analysis is done by first splitting the dataset into clusters and the points that are too far from any of its nearby cluster will be considered as a outlier which can be removed or replaced to reduce noise in the dataset 
			1. Univariate outlier  (Single feature)
			2. Multivaritate outlier (Multi feature) 
			3. Point outlier  (a single point that lies far from the rest)
			4. Contextual outlier (can be noise in data such as punctuation symbols  when realising text analysis etc)
			5. Collective Outlier (novalities in data like a new phenomenon or underlying trend)

Solving discrepency is the first step of the data cleaning process, it may be caused due to human error or error with the method of collection of the dataset etc 


## Data Integration 

Data integration is the process of merging multiple dataset or datasources 

1. Entity Identification Problem (matching schema)
2. Redundancy  and correlation analysis (Data is redundant if it can be derived from another source, chi squared test can be used for this, perform correlation analysis to reduce redundancy)
3. Tuple duplication (when two data rows of the dataset is entirely the same, its a duplicate tuple)
4. Data Value conflict detection and resolution 


## Data Reduction 

Obtaining a reduced form of the dataset in a way that data is much smaller in volume but still produces the same analytical result 

If compression of data is done but restoring the data doesnt lose any information the data reduction is called lossless

PCA, principle component analysis, here the original corelated variables are reduced to smaller set of variables called principal components 