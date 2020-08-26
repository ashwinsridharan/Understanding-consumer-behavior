# Exploring Consumer Behavior using Predictive Analytics

GOAL: To understand and explore consumer behavior to help the manager increase the number of customers buying organic products from the retail store.

## INTRODUCTION
### Supervised Machine Learning 
Supervised learning technique deals primarily with predictive modelling where both the input data and their corresponding output response pairs are fed to the model. This process ensures that the model is trained well enough by analysing the labelled training data to predict the same for new data in the future. Examples include regression and classification.

### Predictive Modelling
Predictive modelling is the process of using known data and results to train, validate and test a model that will predict what will happen in the future. In this process, both the input data and their corresponding output response pairs are fed to the model. This ensures that the model is trained well enough by analysing the labelled training data to predict the same for new data in the future. Examples include regression and classification.

Classification is a supervised learning technique in which the model function classifies the input data into a predefined set of classes or category. The main focus in classification is identify the class to which the data will fall. For example, if we would like to categorize emails in inbox into spam or not spam, we can use a classification model to predict under which category the new email in the inbox will fall into. Based on the training and validation of the model with labelled data, it can classify accurately for other input data in the future.

Classification is different from clustering because clustering is an unsupervised technique where it is all about pattern discovery on its own. The main focus in clustering is to group similar instances together based on their features. This type of machine learning needs no supervision as the input data has no references or labels for the algorithm to learn, enabling it to learn on its own and group the data.

### Data Preparation 
Importing the Dataset

<img src="img/1.png?raw=true"/>

#### Setting model role for target variable ORGYN

<img src="img/2.png?raw=true"/>

### Distribution of ORGYN:

<img src="img/3.png?raw=true"/>

Proportions: 
Total: 22,223
Individuals who did not purchase organic products: 16718 => 75.23% <br>
Individuals who purchased organic products: 5505 => 24.77%

### Variable Selection

<img src="img/4.png?raw=true"/>

Variables that are not included: AGEGRP1, AGEGRP2, NEIGHBORHOOD, LCDATE, ORGANICS <br>
Instead of these we use AGE, NGROUP, LCTIME and ORGYN respectively as these are different measurements for the same information.

### Data Partioning

Splitting the data set into 70% Training and 30% Validation sets:

<img src="img/5.png?raw=true"/>

### Building the machine learning classification model: Decision Tree

<img src="img/6.png?raw=true"/>

### Model Evaluation

The decision tree before pruning has 37 leaves:

<img src="img/7.png?raw=true"/>

Model Assessment Metric: Average Squared Error

<img src="img/8.png?raw=true"/>

#### Parameter Tuning
Pruning: We identify the lowest of the average square error of the validation (0.263877) occurs at the point where the decision tree is having 25 leaves. Therefore, we decide to prune the tree to that point to 25 leaves as the validation error begins to rise from that point onwards again. This is essentially done to prevent overfitting the model as it will start to pick up more noises while it tries to exactly match the training data and fail to predict future data reliably.

Number of leaves in the pruned tree: 25

<img src="img/9.png?raw=true"/>

### Results
Information gain <br>
Information gain is the reduction of entropy which measures how noisy a set of data is. <br>
For a decision tree, information gain gives the worth of the variable i.e. how much information gain is achieved by splitting the node in a decision tree. When we are splitting a decision tree, we would be interested to know how much of information gain is achieved by splitting on that variable as higher the information gain, better the split as it is closer to purity. 

<img src="img/10.png?raw=true"/>

Variable used for the first split: AGE <br>
The competing splits for the first split were: AFFL, GENDER, BILL and CLASS. But AGE has the highest information gain among other variable splits and has a very good margin of almost twice that of the next closest competitive variable AFFL. 

#### Predictions
The variables that were important for growing this tree are: AGE, AFFL & GENDER <br>
Therefore, the most important interpretation for the supermarket manager is that these three variables are the best predictors whether the customer would buy the organic products or not. <br>
These 3 variables out of all the other variables used as inputs in the model best determine our outcome variable ORGYNS to identify whether the customers would be purchasing organic products. So, the manager could make better decisions like: <br>
1. Giving better offers to customers while having these 3 parameters in mind <br>
2. Placing items in a more accessible and eye-catching way to a particular segment, for example happy hours for men/ women <br>
3. Special targeted promotions based on the 3 parameters to offer an overall customized shopping experience


