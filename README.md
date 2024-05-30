# SUPERSTORE SALES MARKETTING PROJECT PORFOLIO

![pexels-goumbik-577210](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/28457cfa-7845-4c73-9cf9-8416139f266a)


## Table of Contents
  - Objective 
- Data Source
- Stages
- Design
  - Mockup
   - Tools
- Development
   - Pseudocode
   - Data Exploration
   - Data Cleaning
   - Transform the Data
   - Create the SQL View
- Testing
  - Data Quality Tests
- Visualization
  - Results
  - DAX Measures
-  Analysis
    - Findings
     - Validation
    - Discovery
 - Recommendations
    - Potential ROI
    -  Potential Courses of Actions 
 - Conclusion

# Objective
Key Point
 - The primary objective of the Superstore Sales Marketing Project Portfolio is to leverage data analysis to gain comprehensive insights into the sales performance and marketing effectiveness across various dimensions of the superstore's operations. By examining a dataset containing crucial sales information, this project aims to identify trends, patterns, and correlations that can inform strategic decision-making and optimize marketing efforts. The analysis will focus on the following key areas:
  1. Sales Performance Analysis:
     - Evaluate overall sales performance by analyzing revenue, profit, and quantity sold across different categories, sub-categories, and products.
  2. Customer Segmentation:
     - Analyze customer data to segment the customer base by various criteria such as segment, state, county, and region.
  3. Geographical Analysis:
     - Assess sales distribution and performance across various states, counties, markets, and regions.
  4. Shipping and Delivery Insights:
     - Examine the impact of different ship modes on customer satisfaction and profitability.
     - Optimize shipping strategies to balance cost-effectiveness with customer satisfaction.
 5. Market and Segment Trends:
    - Analyze sales trends in different market segments to understand market dynamics and consumer behavior.
 6. Profitability Analysis:
    - Identify key drivers of profit and areas where cost reduction can be implemented without compromising sales.

Ideal Solition
- To achieve the objectives outlined for the Superstore Sales Marketing Project Portfolio, the ideal solution involves a comprehensive data analysis approach that includes data preparation, exploratory data analysis (EDA), advanced analytics and the implementation of data-driven recommendation by providing power bi dashboard report that incudes their:
  - Oder IDs
  - Profits
  - Quantity
  - Revenue

This will help to know the the general growth of the Superstore Sales Marketing and specific areas that needs potential improvement.
# Data Source

Data needed to achieve this objectives and solutions is the following:
- SuperStoreOrders dataset that includes the folling columns:
    - Order_Id
    - Date
     - Ship_Mode
     -  Customer_Name
     -  Segment
     -   State
     -  County
    - Market
     - Region
     - Category
    - Sub_Category
  - Product_Name
  - Revenue
   - Quantity
   - Profit
- The data is sourced from Kaggle (an Excel extract),
# Stages
- Design
- Developement
- Testing
- Analysis
# Dashboard Components Requirement
- The following are questions that the dashboard will answer.
  - Top States With Highest Revenue Contributions
  - Categories With Highest Quantity Contributions
  - Monthly Trends For Profits
  - Top 10 Customers With Highest Revenue Contributions
  - Ship Modes With Highest Quantity Contributions
  - Sub Categories With Highest Profits Contributions

For now, these are some of the questions we need to answer, this may change as we progress down our analysis
# Dashboard Mockup
Some of the data visuals that may be appropriate in answering our questions include:
1. Horizontal Bar Charts
2. Column Bar Chart
3. Table
4. Dunut Charts
5. Area Chart
6. Ribbon Chart
7. Tree Map
![SUMMARY_1716982040869429](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/5197ef06-0465-48d7-9bf8-30ed803be45f)
![OVERVIEW_1716982041714386](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/f7bf5336-c88f-4a76-9a55-8a781c3eba20)

# Tools
| Tool | Purpose |        
|------------|------------|
| Excel | Exploring the data | 
| SQL Server  | Cleaning, testing, and analyzing the data    | 
| Power BI  | Visualizing the data via interactive dashboards  | 
| GitHub  | 	Hosting the project documentation and version control  | 
| Mokkup AI   | 	Designing the wireframe/mockup of the dashboard  | 

# Development
# Pseudocode
- The general approach in creating this solution from start to finish was:
 1. Get the data
 2. Explore the data in Excel
 3. Load the data into SQL Server
 4. Clean the data with SQL
 5. Test the data with SQL
 6. Visualize the data in Power BI
 7. Generate the findings based on the insights
 8. Write the documentation + commentary
 9. Publish the data to GitHub Pages
# Data exploration notes
- The Following was my initial observation that caught my Attention:
  1. Analysis of Sales Performance: Revenue and profit data can be analyzed to determine the financial performance of various products, categories, and segments.
  2. Customer Segmentation:Segment, state, and county data can be used to segment customers and tailor marketing strategies.
  3. Geographical Insights:Market and region data provide insights into sales distribution and performance across different geographical areas.
  4. Product Performance:Category, sub-category, and product name details help in analyzing the popularity and profitability of specific products.
  5. Shipping and Delivery:Ship mode data allows for the analysis of shipping preferences and their impact on sales and customer satisfaction.
      
# Data cleaning
 - Expectations to the data.
 
  The aim is to refine our dataset to ensure it is structured and ready for analysis.

The cleaned data should meet the following criteria and constraints:
1. No duplicates in records,this will indicate correct analysis for each record in the dataset.
2. Only relevant columns should be retained.
3. All data types should be appropriate for the contents of each column.
4. No column should contain null values, indicating complete data for all records.
5. Columns like(Revenue,Quantity and Profit)should not contain 0 values for it will not make any sense at all.

And here is a tabular representation of the expected schema for the clean data:
| Column Name| Data Type|   Nullable     |
|------------|------------|--------|
| Order_Id| VARCHAR|     NO  |
|Date|DATE|NO     
|Ship_Mode| VARCHAR|NO
|Customer_Name|VARCHAR|NO
|Segment|VARCHAR|NO
|State|VARCHAR|NO
|County|VARCHAR|NO
|Market|VARCHAR|NO    
|Region|VARCHAR|NO    
|Category| VARCHAR|NO 
|Sub_Category|VARCHAR|NO
|Product_Name|VARCHAR|NO
|Revenue|INTEGER|NO
|Quantity|INTEGER|NO
|Profit|FLOAT|NO
# Transform the data
OUTPUT

![Data Transformation](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/77e9b71c-e4fd-41e2-8c53-8b719541b006)

# Create the SQL view
OUTPUT

![Transform super img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/3e2d8838-9040-4695-bea4-c81cfe5f2b3c)

# Removing Duplicates  in Order Ids
# Duplicates 
SQL Query
  
    SELECT order_id,
 
    ROW_NUMBER() over(PARTITION BY  order_id ORDER BY order_id )ROW_RANK
 
    FROM SuperStore_Sales_Marketing

OUTPUT

![removing duplicates img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/17705eff-da4b-47a5-af4f-75eba95d9131)

- There were several duplicates encountered in the records
# Removal Of Duplicates Using CTEs
SQL Query

    WITH REMOVAL AS
 
    (SELECT order_id,
 
     ROW_NUMBER() over(PARTITION BY  order_id ORDER BY order_id )ROW_RANK
 
    FROM SuperStore_Sales_Marketing)

     DELETE FROM SuperStore_Sales_Marketing
 
     WHERE order_id IN(SELECT order_id
                   
             FROM REMOVAL
                  
             WHERE   ROW_RANK>1 )
                                   
OUTPUT

![ctes removal of duplicates](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/02093cb1-d98c-45ff-9cd3-9637a74132b1)

- All Duplicates were managed to be removed so that we can remain with single unique order ids for analysis.
# Removal Of Null Values
SQL Query
  
    SELECT product_name,
   
    COUNT(*)Null_Records
  
    FROM SuperStore_Sales_Marketing
 
    WHERE product_name IS NULL
  
    GROUP BY product_name
OUTPUT    

![Null records img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/fdaf5b08-c1a9-46de-a881-b632ab1a6a33)

 - There was no null record encountered in the data the rest of columns were clean.
# Zero Values Count Check In Revenue,Quantity And Profit Columns.
SQL Query

    SELECT Revenue,

    COUNT(*)Zero_Values_Count

    FROM SuperStore_Sales_Marketing

    WHERE Revenue =0

    GROUP BY Revenue
OUTPUT  

![Zero Values Check img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/4622ba1e-0b0d-4094-8f14-95f3d9e11c8f)

  THere were no zero values in Revenue ,Quantity and Profit Columns indicating valid data.
# Testing
Here are the data quality tests conducted:
# Row count check
SQL Query

    SELECT COUNT(*)Row_Count_Check

    FROM SuperStore_Sales_Marketing
 OUTPUT 

 ![Row count Check img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/4ba3ef29-c32a-404d-a533-17d366882900)

- All rows are correct.
# Column count check
SQL Query

    SELECT COUNT(*)Column_Count_Check

    FROM INFORMATION_SCHEMA.COLUMNS
 
    WHERE TABLE_NAME='SuperStore_Sales_Marketing'
 OUTPUT 

 
![Column Count Check](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/1a350be4-5d73-4ce0-8a9d-f3b50106362f)

- All columns are correct.
# Data type check
SQL Query

    SELECT COLUMN_NAME,

    DATA_TYPE

    FROM INFORMATION_SCHEMA.COLUMNS
 
    WHERE TABLE_NAME='SuperStore_Sales_Marketing'
 OUTPUT 

 ![data type check](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/f135ca32-784e-45e1-8c0d-6e12eee9f417)

- All data types are correct.

# Duplicates Count Check
SQL Query

    SELECT Order_Id,

    COUNT(*)Duplicates_Count

    FROM SuperStore_Sales_Marketing

    GROUP BY Order_Id

    HAVING COUNT(*)>1
 OUTPUT 

 ![Duplicates count](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/0af2f7f2-0bfe-481e-a0b6-e50311563d4b)

- No Duplicates Encountered Meaning All Records passed the test.
# Visualization
- Results

  This is the look of dashboard.

  ![Power bi dashboard sumary img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/a98e1e89-79cd-4403-ba41-b13af3584380)
![overview pages power bi dashboard img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/faf56ed5-37b0-4212-9f2f-5cc514b50671)
# DAX Measures
# 1. Total Orders
    Total Orders = 
    
    VAR oderids=COUNT(superstore_sales_data[Order_Id])
    
    RETURN oderids
  # 2. Total Revenue
    Total Revenue = 
    
    VAR sumofrevenue=SUM(superstore_sales_data[Revenue])
   
    RETURN sumofrevenue
  # 3. Total Quantity
    Total Quantity = 
    
    VAR sumofquantity=SUM(superstore_sales_data[Quantity])
    
    RETURN sumofquantity
  # 4. Total Profits
    Total Profits = 
    
    VAR sumofprofit=SUM(superstore_sales_data[Profit])
    
    RETURN sumofprofit
  # Analysis
  # Findings
  For this analysis,the following are what we need to find out
  1. Top 10 States With highest Revenue contributions.
  2. Top 10 Customers With highest Revenue Contributions.
  3. Total Quantities Per @ Category.
  4. Total Quantities Per @ Ship Mode.
  5. Monthly Trend For Profits.
  6. Top 10 Sub categories With Highest profits Contributions.
  7. Top 5 Regoinns With Highest profits Contributions.
  8. Total Profits Per @ Market Contributions.
  9. Table Grid Showing SuperStore Sales growth.
  10. Bottom 5 states,customers,categories and sub categories.

# Top 10 States With highest Revenue contributions.
|Rank|State|Total Revenue(K)
|---------|--------|---------|
|1|England|$110481
|2|California|$96606
|3|New York| $75842
|4|New South Wales| $65297
|5|Queensland|$62936
|6|Ile-de-France|$58119
|7|Victoria|$44847
|8|National Capital|$41745
|9|San Salvador|$40694
|10|North Rhine-Westphalia|$38298
# Top 10 Customers With highest Revenue Contributions.
|Rank|Customer Name|Total Revenue(K)
|---------|--------|---------|
|1|Adrian Barton|$14451
|2|Hunter Lopez|$13172
|3|Charles McCrossin| $12759
|4|Joseph Holt| $12597
|5|Mike Gockenbach|$11809
|6|Aaron Hawkins|$11615
|7|Natalie Fritzler|$11424
|8|Carl Ludwig|$11023
|9|Denny Joyr|$10306
|10|Alejandro Savely|$10034

# Total Quantities Per @ Category
|Rank|Category|Total Quantity
|---------|--------|---------|
|1|Office Supplies|$25275
|2|Furniture|$8602
|3|Technology| $8155
# Total Quantities Per @ Ship Mode.















