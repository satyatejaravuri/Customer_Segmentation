# Customer_Segmentation
In this project, a RFM model is implemented to relate to customers in each segment. Assessed the Data Quality, performed EDA using Python and created Dashboard using Power BI


## Data Analytics Customer Segmentation

### Goal of the project

The purpose of this project is to conduct a Customer Segmentation Analysis for an Automobile bike Company. Customer segmentation is performed by developing a RFM Model. RFM (Recency, Frequency, Monetary) analysis is a behavior-based approach grouping customers into segments. It groups the customers on the basis of their previous purchase transactions. In this analysis the customer segment was divided into 11 groups. The analysis will help in determining which customers segments should be targeted in order to enhance sales revenue for the company. A Sales Dashboard for Customer Segmentation is developed using power bi and the data quality assessment and analysis is done using Python.

## Power BI Dashboard

The Sales Dashboard for Customer Segmentation can be found here.

# Analysis Approach

# 1. Data Quality Assessment and Data Cleaning

The first step towards generating useful insights from the data was the data prepartion, quality assessment and data cleaning step. After the cleaning process exploratory data analysis on the dataset and identification customer purchasing behaviours to generate insights can be performed.

In the data cleaning step the data quality of the following datasets were first assesed. After a data quality assessment the following data quality issues was observed and the necessary process to mitigate the issue was followed :

* ###  CustomerDemographics.xlsx :
  
    *  1 Irrelevent column was present and such columns were dropped from the dataset.
    *  There were 5 columns were Missing values were present. For such columns based on the volumne of the missing values either the records were dropped or appropiate values were imputed at places of missing values
    *  For gender column there was no standardisation of data. Based on the values available the column data was standardised to remove data inconsistency.
    *  The Date of Birth column was transformed to create a new feature column 'Age' and 'Age Group' to check for discripency of age distribution. An outlier was observed and the record was removed.
    *  Checked whether there are duplicate records present in the dataset. In this dataset there were no duplicate records.

* ### NewCustomerList.xlsx :
    * 5 Irrelevent column was present and such columns were dropped from the dataset.
    * There were 4 columns were Missing values were present. For such columns based on the volumne of the missing values either the records were dropped or appropiate values were imputed at places of missing values
    * The Date of Birth column was transformed to create a new feature column 'Age' and 'Age Group' to check for discripency of age distribution.
    * There was no data inconsistency.
    * Checked whether there are duplicate records present in the dataset. In this dataset there were no duplicate records.

* ### Transaction_data.xlsx :
   * The product_first_sold_date column is not in datetime format. The data type of this column was changed from int64 to datetime format.
   * There were 7 columns were Missing values were present. For such columns based on the volumne of the missing values either the records were dropped or appropiate values were imputed at places of missing values
   * A new feature column 'Profit' was created which is basically the difference between list price and standard price.
   * There was no data inconsistency.
   * Checked whether there are duplicate records present in the dataset. In this dataset there were no duplicate records.

* ### CustomerAddress.xlsx :
   *For states column there was no standardisation of data. Based on the values available the column data was standardised to remove data inconsistency.
  *There were certain customer IDs from Customer Dempgraphics table which were getting dropped in the Address table.

* # 2. Exploratory Data Analysis on Customer Segments
After the data cleaning process, exploratory analysis on the dataset is performed and the following insights are obtained :

* ### New vs Old Customers Age Distribution
     * Most New customers are aged between 40-49 also for Old Customers the most of them are aged between 40-49
     * The lowest number of customers for both the types of customers is present in the age bracket under 20 and above 80 age groups.
     * The automobile company is popular among New Customers among the age groups 20-29 and 40-49.
     * A steep drop in customers is observed in the 30-39 age group among the New Customers
 

| Old Customers by Age Distribution | New Customers by Age Distribution     | 
| :-------- | :------- | 
| ![Old Customers Age Distribution](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/97587cd5-b28f-42b8-b7b2-2b4797780f98)      | ![New Customers Age Distribution](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/7db6ed2a-b001-4207-902b-b59761c71938) | 



* ### Bike purchases over last 3 years by Gender
    * Most bike puechases are done by Feamale over the last 3 years. Approximately 51% of the bike purchases are done by Female compared to 49% of the purchases being done by Male.
    * The Female purchases are 10,000 more than that of Male purchases (numerically
![Female vs Male Bike Purchases](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/c2cd48ec-fafb-4298-b343-1c89d80800fc)

* ### New vs Old Customers Job Industry Distribution
   * Most New customers are from the Manufacturing and Financial Services sector (approx 20% of the New Customers).
   * The lowest number of customers are from the Agriculture and Telecom sector approx 3%.
   * Similar trend is observed among Old Customers as well.
 
| Old Customers by Job Industry	 | New Customers by Job Industry     | 
| :-------- | :------- | 
| ![Old Customers Age Distribution](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/75534639-2537-4788-8b95-77e3b5461d21)      | ![New Customers Job Industry](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/ab140391-50e5-4f0d-a9fc-da34ff88c657) | 


* ### Wealth Segmentation by Age Category
   * Across all age categories the largest number of customers are from 'Mass Customer' Segment
   * The next category comes from the 'High Net Worth' customers.
   *In the age group 40-49, Affluent segment out performs the High Net Worth customers in terms of number of customers.

| Old Customers Wealth by Age Group | New Customers Wealth by Age Group     | 
| :-------- | :------- | 
| ![Old Customers Wealth Segment](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/83e5e79d-5bbe-4643-96fd-4458bc3ae35b)      | ![New Customer Wealth Segment](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/c83abe36-4151-468a-b85f-b1c8f3a83396) | 

* ### Cars owned by States
   * New South Wales has the largest number of people who donot own a car.
   * In Victoria the proportion is quite even.
   * In Queensland the number of people owning a car is greater than who donot have a car.
     
![Car Owners by State](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/e66fff66-04f0-4b5a-b356-9102ffefecbd)

# 3. RFM Analysis and Customer Segmentation

In this stage of analysis the customer segmentation was done by developing an RFM Model. The RFM (Recency, Frequency, Monetary) analysis is a behavior-based approach grouping customers into segments. It groups the customers on the basis of their previous purchase transactions.

In this analysis the customer segment was divided into 11 groups. The groups being :
* Platinum Customers
* Very Loyal Customers
* Recent Customers
* Potential Customers
* Lost Customers
* Losing Customers
* Late Bloomer
* High Risk Customers
* Evasive Customers
* Becoming Loyal
* Almost lost Customers

As of the current state of the Automobile business the current distribution of customers segments is depicted below:

![Customer Segment Distribution](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/6f3f3087-0431-424f-9461-4605fe237b09)


## 4. RFM Analysis: Scatter Plots
## Recency vs Monetary :

The visualization shows that recent customers have purchased more products and generated relatively more revenue than the customers who visited a while ageo.

![Recency vs Monetary](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/8c144e50-4786-4a36-a12b-d77bacb7588e)


## Frequency vs Monetary :
The visualization shows that customers belonging to Platinum/ Very Loyal/ Becoming Loyal Customer Segments have a greater frequency and generate greater monetary for the business

![Frequency vs Monetary](https://github.com/satyatejaravuri/Customer_Segmentation/assets/31037816/d49906d0-7227-4b0b-9e26-e112ac24e6ed)

# Datasets Used
The datasets used include:

* ##  Raw_data.xlsx:## This excel file dataset included the following sheets of data:
    * Transactions_data.xlsx: This dataset included the transactions data of the customers across all the different states in Australia.
    * NewCustomerList.xlsx: This dataset included the new customers who visted the automobile bike company recently.
    * CustomerDemographic.xlsx: This dataset included entire details of the Customer Demographics.
    * CustomerAddress.xlsx: This dataset included the address of the Customers.


