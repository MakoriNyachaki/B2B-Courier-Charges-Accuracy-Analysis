### B2B Ecommerce Fraud: Case Study

##### Problem Statement

In today's dynamic e-commerce industry, fast and efficient order delivery is essential to business success. There is an urgency  to ensure a seamless order fulfillment, which creates a need for the e-commerce companies to partner with courier service companies. To manage charges collected by courier companies is a burdensome task. Therefore, this is one of the real-time problems B2B businesses go through when their estimated charges don't match in their invoices. We will use Python in trying to counter the problem.
The whole problem and dataset for ABC can be accessed from [here](https://statso.io/b2b-ecommerce-fraud-case-study/#google_vignette)

##### Scope
The goal of B2B courier charges accuracy study is to evaluate how accurately courier companies charge for the delivery of products in business-to-business transactions. Ensuring that businesses receive accurate invoices for the services rendered by courier providers is the goal.

##### Steps
1. Import the important Python Libraries to be used:
    _Example importing pandas_
        '''import pandas as pd'''
2. View part of the reports to see and  the structure of the dataset.
        '''pd.read_csv(<file_name>)'''
3. Look at the missing values in the data. We use the isnull() and sum() functions to determine missing values in each report file.
        '''file_name.isnull().sum()'''
4. Let us do the data cleaning by dropping the columns missing values. We use the '''drop()''' function to achieve this.

