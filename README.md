# Fitbit-calories predection model 
 This Project was done by the help of https://ineuron.ai/,
 For more details about the project go through the docomentation file

# Problem Statement
To build a regression model to predict the calories burnt based on the given indicators in the training data. 

# Prediction Data Description
 
Client will send the data in multiple set of files in batches at a given location. Data will contain climate indicators in 10 columns.
Apart from prediction files, we also require a "schema" file from client which contains all the relevant information about the training files such as:
Name of the files, Length of Date value in FileName, Length of Time value in FileName, Number of Columns, Name of the Columns and their datatype.


#Prediction 
 
1) Data Export from Db - The data in the stored database is exported as a CSV file to be used for prediction.
2) Data Preprocessing   
   a) Drop columns not useful for training the model. Such columns were selected while doing the EDA.
   b) Replace the invalid values with numpy “nan” so we can use imputer on such values.
   c) Check for null values in the columns. If present, impute the null values.
   d) Scale the training data.
3) Clustering - KMeans model created during training is loaded, and clusters for the preprocessed prediction data is predicted.
4) Prediction - Based on the cluster number, the respective model is loaded and is used to predict the data for that cluster.
5) Once the prediction is made for all the clusters, the predictions along with the original names before label encoder are saved in a CSV file at a given location and the location is returned to the client.
 
# Deployment

We will be deploying the model to the Pivotal Web Services Platform. 
This is a workflow diagram for the prediction of using the trained model.                  
