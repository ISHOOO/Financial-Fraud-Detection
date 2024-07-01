# Financial-Fraud-Detection
A fraud detection model built using random forests and rule based classifier. It detects fraud in financial transactions based on predictive features such as transaction amount, payer type (customer/business), reciever type (customer/business), reciever account balance and payer account balance. The dimensions of training data are 6362620 x 11 and achives a validation accuracy of about 100% on the given validation data. 

## About the dataset
Open available on Kaggle: ![Fraudulent Transactions Data](https://www.kaggle.com/datasets/chitwanmanchanda/fraudulent-transactions-data)
size of the dataset: 6,362,620 rows and 10 columns
Data Dictionary:
1. step - maps a unit of time in the real world. In this case 1 step is 1 hour of time. Total steps 744 (30 days simulation).
2. type - CASH-IN, CASH-OUT, DEBIT, PAYMENT and TRANSFER.
3. amount - amount of the transaction in local currency.
4. nameOrig - customer who started the transaction
5. oldbalanceOrg - initial balance before the transaction
6. newbalanceOrig - new balance after the transaction
7. nameDest - customer who is the recipient of the transaction
8. oldbalanceDest - initial balance recipient before the transaction. Note that there is not information for customers that start with M (Merchants).
9. newbalanceDest - new balance recipient after the transaction. Note that there is not information for customers that start with M (Merchants).
10. isFraud - This is the transactions made by the fraudulent agents inside the simulation. In this specific dataset the fraudulent behavior of the agents aims to profit by taking control or customers accounts and try to empty the funds by transferring to another account and then cashing out of the system.
