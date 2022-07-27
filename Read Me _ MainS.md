# Read Me :
Note that there is also another file called Servier PCA where we studied the problem after applying dimension reduction. 
## The datasets
### Step 1: Loading and analysing the datasets.
There are two datasets, which we treated as dataset_single and dataset_multi. They had no null values. dataset_single consisted of 3 rows with 2 rows denoting molecule id and smiles respectively while one row called P1 was the predictor variable which signified the presence or absence of a certain property in the molecule. The goal is to predict using machine learning models the row P1. So this is a binary classification problem. The prediction set P1 is imbalanced with the 0 value to 1 value roughly in the ration of 1:4.
#### Servier Main.readme
#### Model 1
In this model, we had to use dataset_single and extract features from smiles column using fingerprint features. This gave us 2048 features for each molecule using which we had to predict P1. 
##### DNN Models.
We first trained a baseline model with the original dataset and then a deeper model with the balanced dataset_single  with  4 hidden layers and RELU and sigmoid activation functions along with binary cross-entropy loss function and ADAM optimiser. After training the deep model using the balanced dataset, we obtained a Test accuracy of 98 percent, which we saved as Model_1.

#### Model 2
In this model, we had to use dataset_single and predict using only the smiles column. Using sklearn hashing we converted the categorical smiles column to numeric and used 2048 features like in the previous and then used deep neural networks with  4 hidden layers and RELU and sigmoid activation functions along with binary cross-entropy loss function and ADAM optimiser.After training the deep model using the balanced dataset, we obtained a Test accuracy of 71.6 percent, which we saved as Model_2.

#### Model 3
In this model, we had to use dataset_multi and predict using either Model 1 architecture or Model 2 architecture the features P1, P2, P3, P4, P5, P6, P7, P8, P9. We trained a deep neural network with  4 hidden layers and RELU and sigmoid activation functions along with categorical cross-entropy loss function and ADAM optimiser. After training the deep model we obtained a Test accuracy of 29.6 percent. We need to improve this model.  

#### Servier PCA.readme 

We did feature reduction using Principal Component Analysis on the 2048 features, reducing it to 11 features and then trained the Model 1. First we did analysis with the classical machine learning models (without deep learning), but the accuracy was low on the test set. After that we implemented a deep learning model. For Model 2, we used feature hashing and then created a small feature dimension of 11 features and trained the Model using deep learning. For Model 3, we used the same training as the previous.