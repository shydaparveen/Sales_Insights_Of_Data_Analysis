# Project : Sales Insights of Data Analysis-AtliQ Hardware
## Problem Statement :
### In this project performed India based AtliQ hardware company sales insights - A Data Analysis project.

AtliQ Hardware is a company which supplies computer hardware and peripherals to many of clients such as surge stores, Nomad stores etc. across India. AtliQ Hardware head office is situated in Delhi, India and they have many regional office through out the India.

Sales director for this company is facing a lot of challenges is this the market is growing dynamically and sales director is facing issue in terms of tracking the sales in this dynamical growth market and he is having issues with growth of this bussiness, as overall sales was declining. He has regional manager for North India, South and Central India. Whenever he wants to get insights of thses region he would call these people and on the phone regional manager give some insights to him that this was the sales last quarter and we are going to grow by this much in the next quarter.

The problem was that all thses thing happening is verbal and these was mo proof with facts that how his business is affected and which made him frustraed as he can see that overall sales is declining but when he can ask regional manager, he is not getting complete picture of this bussiness and when he and this AtliQ hardware is big business. so to see insights clearly. and he will get proper insights anbd can take data driven decision to increase sales of hos company. All he wants is a simple data visualization tool which he can access on daily basis. By using such tools and technology one can make data driven decisiions which helps to increase the sales of the company. So, In this projects we will help a company make its own sales related dashboard using power BI.
## Data Discovery :

#### Project Planning using AIMS Grid -
It is a project management tool which consists of four components-

Purpose - (What to do exactly)
Stackholder - (Who will be involved)
End result - (What do you want to achieve)
Success Criteria - (Cost optimization and time save)
AIMS Grid -
1. Purpose :- To unlock sales insights that are not visible before for the sales them for decision support and automate them to reduced manual time spent in data gathering.

2. Stakeholders :-

Sales Director
Marketing Team
Customer Service Team
Data and Analytics Team
IT
3. End result :- An automated dashboard providing quick and latest sights in order to support Data driven decision making.

4. Success Criteria :-

Dahboard uncovering sales order insights with latest data available
Sales team able to take better decisions and prove 10% cost saving of total spend.
Sales analysis stop data gathering manually in order to save 20% business time andreinvest it value added activity.

## Data Analysis using MySQL :
Completed the Data discovery and then used mySQL for data analysis.

SQL database dump is in db_dump.sql file above. Download db_dump.sql file to your local computer

Importing Data to MySQL workbench
The import of data is done from an already existing MySQL file. This file has to be loaded into MySQL workbench for further data analysis.

Analysis of data by looking into different tables and reflecting garbage values

We can see that garbage value that the table market cantains certain values which are incorrect.

SELECT * FROM sales.market;

And then we can check that transacation table we can see that ceratin negative value in amount which is not possible. and we can see that certain transactions are in USD. Hence, filtration of that is also needed by converting into INR.

SELECT * FROM sales.transactions;

### Analysis of different SQL statement on data base

1.To find of all customers records

SELECT * FROM sales.customers;

2.To find total number of customers

SELECT count(*) From sales.customers;

3.To find transactions for Chennai market (market code for chennai is Mark001

SELECT * FROM sales.transactions where market_code='Mark001';

4.To find distrinct product codes that were sold in chennai

SELECT distinct product_code FROM sales.transactions where market_code='Mark001';

5.To find transactions for Chennai market (market code for chennai is Mark002

SELECT * FROM sales.transactions where market_code='Mark002';

6.To find distrinct product codes that were sold in mumbai

SELECT distinct product_code FROM sales.transactions where market_code='Mark002';

7.To find transactions where currency is US dollars

SELECT * from sales.transactions where currency="USD";

8.To find transactions in 2020 join by date table

SELECT sales.transactions.*, sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020;

8.To find transactions in 2019 join by date table

SELECT sales.transactions.*, sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2019;

9.To find total revenue in year 2020,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";

10.To find total revenue in year 2019,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2019 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";

11.To find total revenue in year 2020, January Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="January" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

12.To find total revenue in year 2020, February Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="February" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

13.To find total revenue in year 2019, January Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="January" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

14.To find total revenue in year 2019, February Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="February" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

15.To find total revenue in year 2020 in Chennai

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.market_code="Mark001";

16.To find total revenue in year 2020 in Mumbai

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.market_code="Mark002";

Similarly, if we want different of any other particular city the market code of that city is used on the mysql workbench.

## Data Cleaning and ETL (Extract, Transform, Load):
### In this process, we are work on data cleaning and ETL.

Step 1: Connect the MySQL database with the PowerBI desktop.

Step 2: Loading data into the Power BI deskstop. This step load all the tables and created in the data base. This load option will connect with the SQL and pull all the records into power BI environment.

In that model view looking up for model which form the star schema.

### Data_Model

Setp 3: Transform data with the help of Power Query

Perform filtration in market’s table: In the tables perform when we click on the transform data option, we are directed to Power query editor. Power query editor is where we perform out ETL.and then we can perform data transformation i.e. Data Cleaning, Data Wrangling, Data Munging. we need to filter the rows where the values are null and filtering the data and deselecting the blank option.

Perform filtration in Transaction’s table: In the table perform when we check the query in the MySQL to filter some negative values and also 0 values that appears in the table, the desired output is received.and we will perform the similar filtration in PowerBI. we have deselecting the values, don’t want in the table. The result after filtration. the zero values represent some garbage values which is not possible so we need to clean that data.

Convert USD into INR in the transaction’s table: the AtliQ Hardware only works in India so the USD values are not possible. we need to convert those USD values into INR by using some formulas. Add new column - Conditional column - normalized currency where sales amount will be in INR

In power query editore finding the total values having USD as currency.

 `=Table.AddColumn(#"Filtered Rows", "norm_sales_amount",each if [currency] = "USD" then [sales_amount]*75 else [sales_amount]`
using this correct formula of the conversion,and converted the USD currency into INR.

### In MySQL Workbench find that there are duplicates of USD and INR

 `SELECT count(*) from sales.transactions where sales.transactions.currency="INR\r";` 
 150000 - can't removed as it is large amount

 `SELECT count(*) from sales.transactions where sales.transactions.currency="INR";` 
 279 - we can remove it as it is small record and can be considered as bad data

 `SELECT count(*) from sales.transactions where sales.transactions.currency="USD\r";` 

 `SELECT count(*) from sales.transactions where sales.transactions.currency="USD";`

 `SELECT * from sales.transactions where sales.transactions.currency='USD\r' or sales.transactions.currency='USD';`
we can see that it is duplicate and for analysis its better to delete anyone of them so lets delete USD and keep USD/r. finally we will keep data with INR/r and USD/r-

### Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.

#### Data Analysis (DAX):
Measures used in all visualization are:

#### Key Measures:

Profit Margin % = DIVIDE([Total Profit Margin],[Revenue],0)
Profit Margin Contribution % = DIVIDE([Total Profit Margin],CALCULATE([Total Profit Margin],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))
Revenue = SUM('sales transactions'[sales_amount])
Revenue Contribution % = DIVIDE([Revenue],CALCULATE([Revenue],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))
Revenue LY = CALCULATE([Revenue],SAMEPERIODLASTYEAR('sales date'[date]))
sales quntity = SUM('sales transactions'[sales_qty])
Total Profit Margin = SUM('Sales transactions'[Profit_Margin])
Profit Target:

Profit Target1 = GENERATESERIES(-0.05, 0.15, 0.01)
Profit Target Value = SELECTEDVALUE('Profit Target1'[Profit Target])
Target Diff = [Profit Margin %]-'Profit Target1'[Profit Target Value]
Build Dashboard Or a Report:
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

# Shows visualizations from Sales insights :
# https://app.powerbi.com/links/QeUg-a_Bpw?ctid=c6e549b3-5f45-4032-aae9-d4244dc5b2c4&pbi_source=linkShare
