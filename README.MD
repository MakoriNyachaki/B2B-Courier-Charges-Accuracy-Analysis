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
4. Let us do the data cleaning by dropping the unnamed columns. We use the _drop()_ function to achieve this.
5. Merge reports according to the common fields. We use the merge() function to achieve the result.

        '''pd.merge(<dataframe1>, <dataframe2>, on=<common_field>)'''
        
The _ExternalOrderNo_ is nothing but the _Order Id' in other datasets. So we rename it. We use the _rename()_function.

        '''filename.rename(columns = {'oldaname':'newname'})'''

We merge the customer pin code data frame and the courier invoice data frame using the below code:

            '''# Map the courier invoice and pincode mapping based on Pincode
                # First drop duplicates from the pincode

                abc_courier = pinCode.drop_duplicates(subset=['Customer Pincode'])
                courier_abc = invoice[['Order ID', 'Customer        Pincode', 'Type of Shipment']]
                pincodes = courier_abc.merge(abc_courier,on='Customer Pincode')
                print(pincodes.head())'''.

###### How it works
        
Below is how the invoice and pin code data frame merging code works:

    We first extract the unique customer pin codes from the pincode mapping dataset and create a new DataFrame called “abc_courier” to store this information.
    We then select specific columns (“Order ID”, “Customer Pincode”, “Type of Shipment”) from the invoice dataset and create a new DataFrame called “courier_abc” to store this subset of data.
    We then merge the ‘courier_abc’ DataFrame with the ‘abc_courier’ DataFrame based on the ‘Customer Pincode’ column. This merge operation helps us associate customer pin codes with their respective orders and shipping types. The resulting DataFrame is named ‘pincodes’.

6. Then we calculate the different weight clusters for price determination based on the weight of the shipment.
###### How the function works

    The function first calculates the remainder of the weight divided by 1 then the value is rounded off to one decimal place. If the remainder is 0.0, it means the weight is a multiple of 1 kg, and the function returns the weight as it is.
    If the remainder is greater than 0.5, it means that the weight exceeds the next half kg cluster. So the function rounds it to the next integer and adds 1.0 to it, which represents the next heavier slab.
    If the remainder is less than 0.5  it means the weight falls under the current half kg cluster. Then the function rounds the weight to the nearest integer and adds 0.5 to it., which represents the current weight slab.
