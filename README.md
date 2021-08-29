# Bank Customer Churn Predictor 

## Project introduction
Customer retention is paramount to the survival, growth and development of a company. It helps forge strong and lasting relationships with existing customers which not only helps attract new ones, but also provides a steady source of income by increasing a customer's lifetime value. In fact, the probability of selling to an existing customer is around 60-70% whilst the chance of selling to a new prospect ranges from 5-20%. Acquiring new prospects is about 5 times more expensive than retaining existing customers. Finally, increasing customer retention by just 5% can increase profits by 25-95% [[1]](https://www.outboundengine.com/blog/customer-retention-marketing-vs-customer-acquisition-marketing/).

Therefore, it is in the interest of a company or service to be able to determine, using historical data whether a customer will churn (not be retained/exit) in advance in order to take preemptive action and try to retain them. 

In this python notebook, I will attempt to build a model which outputs the likelihood of a customer exiting a bank using the bank customer churn prediction dataset from [Kaggle](https://www.kaggle.com/adammaus/predicting-churn-for-bank-customers). 

## Outline

### Exploratory data analysis 
First, the dataset is explored to draw basic insights and see the relationship between some of the variables and the likelihood of a customer exiting the bank.

### Preparing the data
The data is split into testing and training sets (80-20%) and the categorical covariates are replaced with dummy variables and a reference category. The response and predictors are split. 

### 1st attempt: logistic regression 
I have first attempted to solve this problem by building a logistic regression model. Overall, the model explains some variability in the probability of a customer churning. This is supported by the output which generally shows low p-values for the covariates and a low LLR p-value. However, the confusion matrix suggests that the model has a high Type II error rate and is bad at identifying customers who have churned. This is also supported by a low precision and recall. 

### 2nd attempt: ANN
I then tried solving this problem by building an artificial neural network (ANN). I first standardised the covariates and then designed a 3 hidden layer neural network. The output layer maps the incoming data to a probability via a sigmoid activation function. The neural network showed more promising results, with a lower Type II error rate (about 50%, which is still very high!), a higher accuracy, precision and recall. 
