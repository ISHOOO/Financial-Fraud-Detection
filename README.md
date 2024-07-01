# Financial-Fraud-Detection

## Overview
A fraud detection model built using random forests and rule based classifier. It detects fraud in financial transactions based on predictive features such as transaction amount, payer type (customer/business), reciever type (customer/business), reciever account balance and payer account balance. The model achieves a validation accuracy of about 100% on the given validation data. 

## About the dataset
Openly available on Kaggle: [Fraudulent Transactions Data](https://www.kaggle.com/datasets/chitwanmanchanda/fraudulent-transactions-data)
size of the dataset: 6,362,620 rows and 10 columns
The dataset is significantly imbalanced with respect to the target variable `isFraud` by a margin of 99.1% : 0.9% ratio for positive and negative class respectively
Data Dictionary:
1. **step** - maps a unit of time in the real world. In this case 1 step is 1 hour of time. Total steps 744 (30 days simulation).Data type: int64  
2. **type** - CASH-IN, CASH-OUT, DEBIT, PAYMENT and TRANSFER. data type: object
3. **amount** - amount of the transaction in local currency. data type: float64
4. **nameOrig** - customer who started the transaction. data type: object
5. **oldbalanceOrg** - initial balance before the transaction. data type: float64
6. **newbalanceOrig** - new balance after the transaction. data type: float64
7. **nameDest** - customer who is the recipient of the transaction. data type: object
8. **oldbalanceDest** - initial balance recipient before the transaction. Note that there is not information for customers that start with M (Merchants). data type: float64
9. **newbalanceDest** - new balance recipient after the transaction. Note that there is not information for customers that start with M (Merchants). data type: float64
10. **isFraud** - This is the transactions made by the fraudulent agents inside the simulation. In this specific dataset the fraudulent behavior of the agents aims to profit by taking control or customers accounts and try to empty the funds by transferring to another account and then cashing out of the system. data type: int64


## Libraries used:
1. **Scikit-Learn**: Scikit-learn is a machine learning library for Python that provides simple and efficient tools for data mining and data analysis, including classification, regression, clustering, and dimensionality reduction. Used in the project for performing soplitting and validation data, Label encoding categorical features, building and training Random forest classifier and evaluating it using Confusion matrix and ROC-AUC curve .

    ![scikit learn](https://github.com/ISHOOO/Financial-Fraud-Detection/assets/132544766/293256c7-8e8f-42cd-8110-136d615ca51b)

2. **Pandas**: A powerful data manipulation and analysis library for Python, providing data structures like DataFrames, Series, Sparse, Panel and Collection to efficiently handle and analyze large datasets. Used in the project for data cleaning, preprocessing, feature engineering, and manipulation of the transaction data to prepare it for modeling.

    ![Pandas](https://github.com/ISHOOO/Financial-Fraud-Detection/assets/132544766/7fb05ec4-c840-41ac-bd6f-b2d65078b6b6)

3. **Matplotlib**: A comprehensive library for creating static, animated, and interactive visualizations in Python. Used in the project for plotting and visualizing the distribution of variables, trends, and relationships in the data to gain insights and communicate findings.

    ![matplotlib](https://github.com/ISHOOO/Financial-Fraud-Detection/assets/132544766/038f514d-547b-4aeb-9940-7ac25aab46a4)

4. **Seaborn**: A statistical data visualization library based on Matplotlib that provides a high-level interface for drawing attractive and informative graphics. Used in the project to visualize the confusion matrix, and study multicollinearity between variables using pair plots, heatmaps, and box plots.

    ![seaborn](https://github.com/ISHOOO/Financial-Fraud-Detection/assets/132544766/7048f221-44ce-4f6e-922c-0228123ca20e)


## Methodology:
This project went through various stages throughout its entire lifecycle which are as follows:
1. **Data retrieval**: extracting the dataset and storing it in a dataframe

2. **Data visualization and comprehension**: includes study of various features of the data set and their effect on the final model.

3. **Data Wrangling and Feature engineering**: includes extracting features from existing features, eliminating irrelevant features, detecting outliers and detecting missing values

4. **Data Modeling**: involves splitting the dataset into training and validation sets, defining the feature set and the target variable, hyperparameter tuning and fitting the parameters like weights and biases to training the model.

5. **Model Evalution**: involves plotting the confusion matrix and the ROC-AUC curve, and printing the classification report.

## Features of the model:
1. **Ensemble of multiple learners**: It is a bagging ensemble of 15 decision trees
2. **Information gain**: It uses entropy/information-gain as heuristic to split at a node of each decision tree
3. **rule-based bias**: The model is biased to classify each of those transactions as fraud where the amount is > 200,000

## Evaluating Model Performance:
1. **Classification Report**:
    ![Classification Report](https://github.com/ISHOOO/Financial-Fraud-Detection/assets/132544766/fe4659d6-8a76-482f-bbe0-1c1638a8310a)

2. **Confusion matrix**:
    ![Confusion matrix](https://github.com/ISHOOO/Financial-Fraud-Detection/assets/132544766/624572ef-3b68-44ea-a3a5-dd9e2947faba)

3. **ROC-AUC Curve**:
    ![ROC-AUC](https://github.com/ISHOOO/Financial-Fraud-Detection/assets/132544766/3649a7d4-0ac9-4cbe-bf56-e4a7dfc29238)
