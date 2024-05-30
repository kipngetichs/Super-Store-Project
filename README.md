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

# Removal Of Null Values
SQL Query
  
    SELECT product_name,
   
    COUNT(*)Null_Records
  
    FROM SuperStore_Sales_Marketing
 
    WHERE product_name IS NULL
  
    GROUP BY product_name
OUTPUT    
