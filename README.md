# SUPERSTORE SALES MARKETING PROJECT PORFOLIO
# EXCEL POWER BI AND SQL PROJECT

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
  # Design
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
  7. Top 5 Region With Highest profits Contributions.
  8. Total Profits Per @ Market Contributions.
  9. Table Grid Showing SuperStore Sales growth.
  10. Bottom 5 states,customers,sub categories with lowest profits.

# 1. Top 10 States With highest Revenue contributions.
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
# 2. Top 10 Customers With highest Revenue Contributions.
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

# 3. Total Quantities Per @ Category
|Rank|Category|Total Quantity
|---------|--------|---------|
|1|Office Supplies|25519
|2|Furniture|8697
|3|Technology| 8198
# 4. Total Quantities Per @ Ship Mode.
|Rank|Ship Mode|Total Quantity
|---------|--------|---------|
|1|Standard Class|25493
|2|Second Class|8204
|3|First Class| 6507
|4|Same Day| 2210
# 5. Monthly Trend For Profits.
|Rank|Month Name|Total Profit(K)
|---------|--------|---------|
|1|January|$13010.3
|2|February |$14957.78
|3|March| $21711.78
|4|April| $14902.4
|5|May|$22354.96
|6|June|$33914.27
|7|July|$21692.78
|8|August|$28865.34
|9|September|$37622.28
|10|October|$38232.26
|11|November|$56021.81
|12|December|$47287.82
# 6. Top 10 Sub categories With Highest profits Contributions.
|Rank|Sub Category|Total Profit(K)
|---------|--------|---------|
|1|Copiers|$63648.11
|2|Phones |$63127.32
|3|Bookcases| $38148.80
|4|Chairs| $34111.34
|5|Accessories|$31521.43
|6|Appliances|$29381.39
|7|Storage|$27522.24
|8|Machines|$15553.62
|9|Binders|$14845.57
|10|Paper|$14218.62
# 7. Top 5 Region With Highest profits Contributions.
|Rank|Region|Total Profit(K)
|---------|--------|---------|
|1|Central|$75773.51
|2|North |$51540.79
|3|North Asia| $34587.48
|4|Central Asia| $29105.77
|5|Oceania|$29048.79
# 8. Total Profits Per @ Market Contributions.
|Rank|Market|Total Profit(K)
|---------|--------|---------|
|1|APAC|$105036.18
|2|EU |$70071.61
|3|LATAM| $66530.35
|4|US| $63423.96
|5|Africa|$27319.92
|6|EMEA|$14991.01
|7|Canada|$3200.76
# Bottom 5 States With Highest Loss Contributions
|Rank|States|Total Loss(K)
|---------|--------|---------|
|1|Lagos|$-6746.50
|2|Illinois |$-6582.30
|3|Istanbul| $-6432.10
|4|Stockholm| $-3766.61
|5|Lisboa|$-3671.30
# Bottom 5 customers With Highest Loss Contributions
|Rank|customers|Total Loss(K)
|---------|--------|---------|
|1|Henry Goldwyn|$-3435.69
|2|Saphhira Shifley |$-1841.31
|3|Nancy Lomonaco| $-1581.19
|4|Benjamin Farhat| $-1578.86
|5|Stefania Perrino|$-1532.25
# Bottom 5 Sub category With lowest profits Contributions
|Rank|Sub category |Total Loss(K)
|---------|--------|---------|
|1|Tables|$-20637.02
|2|Fasteners |$3127.39
|3|Labels| $3548.13
|4|Supplies| $4917.93
|5|Envelopes|$6284.33
# Notes
- For this analysis, we'll prioritize analysing with metrics that are important in generating the expected ROI for the project, which are the states,market,customers,categories,sub categories and ship mode with the highest and lowest contributions in the following:
- Total Orders
- Total Revenue
- Total Quantity
- Total Profits
# Validation
# Top States With Highest Income Contributions
Calculation Breakdown

Top State=High Income Growth Contribution
1. England
   - Total Orders=312K
   - Total Revenue=$110481K
   - Total Quantity=1163K
   - Total Profits=$23949.96K
2. New York
   -  Total Orders=292K
   -  Total Revenue=$75842K
   -  Total Quantity=1135K
   -  Total Profits=$16252.99K
3. California
   - Total Orders=520K
   - Total Revenue=$96606K
   - Total Quantity=1958K
   - Total Profits=$15061.26K
 4. New South Wales
     - Total Orders=188K
     - Total Revenue=$65297K
     - Total Quantity=679K
     - Total Profits=$12873.15K
 5. San Salvador
    - Total Orders=158K
    -  Total Revenue=$40694K
    -  Total Quantity=589K
    -  Total Profits=$9630.61K
# SQL query for this :
    SELECT TOP 5  State,

    COUNT(Order_Id)Total_Orders,

    SUM(Revenue)Total_revenue,

    SUM(Quantity)Total_Quantity,

    CAST(SUM(Profit) AS DECIMAL(10,2))Profits

    FROM SuperStore_Sales_Marketing

    GROUP BY  State

    ORDER BY  Profits DESC
# OUTPUT
![Top states income growth](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/07b3a63a-2e7d-4cb4-a3f0-6516b3b06702)

# Top Customers With Highest Income Contributions
Calculation Breakdown

Top Customer=High Income Growth Contribution
1. Adrian Barton
   - Total Orders=21K
   - Total Revenue=$14451K
   - Total Quantity=79K
   - Total Profits=$5545.30K
2. Hunter Lopez
   - Total Orders=12K
   - Total Revenue=$13172K
   - Total Quantity=50K
   - Total Profits= $5321.82K 
3. Mike Gockenbach
   - Total Orders=15K
   - Total Revenue=$11809K
   - Total Quantity=52K
   - Total Profits=$3807.12K 
4. Cynthia Arntzen
   - Total Orders=12K
   - Total Revenue=$8148K
   - Total Quantity=52K
   - Total Profits=$2928.02K
 5. Denny Joy
    - Total Orders=16K
    - Total Revenue=$10306K
    - Total Quantity=65K
    - Total Profits=$2593.34K
  
# SQL query for this :
    SELECT TOP  5 Customer_Name,

    COUNT(Order_Id)Total_Orders,

    SUM(Revenue)Total_revenue,

    SUM(Quantity)Total_Quantity,

    CAST(SUM(Profit) AS DECIMAL(10,2))Profits

    FROM SuperStore_Sales_Marketing

    GROUP BY  Customer_Name

    ORDER BY  Profits DESC
# OUTPUT

![Top Customers img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/b266b154-ca63-4fb5-8a21-d17b65af7f49)

# Top Categories With Highest Income Contributions  
Calculation Breakdown
Top Category=High income Growth
1. Technology
   - Total Orders=2355K
   - Total Revenue=$1122829K
   - Total Quantity=8198K
   - Total Profits=$173850.47K
2. Office Supplies
   - Total Orders=7448K
   - Total Revenue=$855694K
   - Total Quantity=25519K
   - Total Profits=$117166.28K
3. Furniture
   - Total Orders=2454K
   - Total Revenue=$1014213K
   - Total Quantity=8697K
   - Total Profits=$59557.03K
# SQL query for this :
    SELECT Category,

    COUNT(Order_Id)Total_Orders,

    SUM(Revenue)Total_revenue,

    SUM(Quantity)Total_Quantity,

    CAST(SUM(Profit) AS DECIMAL(10,2))Profits

    FROM SuperStore_Sales_Marketing

    GROUP BY  Category

    ORDER BY  Profits DESC
# OUTPUT

![Top categories img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/83276a9d-aad7-4352-829d-56ca13407c93)

# Top Ship Modes With Highest Income Contributions
Calculation Breakdown

Top Ship Mode=High Income Growth

1. Standard Class
   - Total Orders=7344K
   - Total Revenue=$1808006K
   - Total Quantity=25493K
   - Total Profits=$211670.34K
2. Second Class
   - Total Orders=2414K
   - Total Revenue=$588314K
   - Total Quantity=8204K
   - Total Profits=$66756.83K
3. First Class
   - Total Orders=1857K
   - Total Revenue=$448869K
   - Total Quantity=6507K
   - Total Profits=$52970.62K
4. Same Day
   - Total Orders=642K
   - Total Revenue=$147547K
   - Total Quantity=2210K
   - Total Profits=$19175.99K
# SQL query for this :
    SELECT Ship_Mode,

    COUNT(Order_Id)Total_Orders,

    SUM(Revenue)Total_revenue,

    SUM(Quantity)Total_Quantity,

    CAST(SUM(Profit) AS DECIMAL(10,2))Profits

    FROM SuperStore_Sales_Marketing

    GROUP BY  Ship_Mode

    ORDER BY  Profits DESC

# OUTPUT

![Top Ship Modes img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/0404b3aa-b4fe-49c2-bb39-19de0c23cb9c)
# Monthly Trend For Profits.
Calculation Breakdown

Top Month=High Income Growth Contributions

1. January
   - Total Orders=600K
   - Total Revenue=$156174K
   - Total Profits=$13010.30K
   - Total Quantity=2125K
2. February
   - Total Orders=530K
   - Total Revenue=$125181K
   - Total Profits=$14957.78K
   - Total Quantity=1874K
3. March
   - Total Orders=783K
   - Total Revenue=$170391K
   - Total Profits=$21711.78K
   - Total Quantity=2708K
4. April
   - Total Orders=691K
   - Total Revenue=$154528K
   - Total Profits=$14902.40K
   - Total Quantity=2379K
5. May
   - Total Orders=903K
   - Total Revenue=$230108K
   - Total Profits=$22354.96K
   - Total Quantity=3131K
6. June
   - Total Orders=1231K
   - Total Revenue=$294844K
   - Total Profits=$33914.27K
   - Total Quantity=4124K
7. July
   - Total Orders=716K
   - Total Revenue=$177457K
   - Total Profits=$21692.78K
   - Total Quantity=2399k
8. August
   - Total Orders=1159K
   - Total Revenue=$292370K
   - Total Profits=$28865.34K
   - Total Quantity=3906K
9. September
    - Total Orders=1437K
    - Total Revenue=$323451K
    - Total Profits=$37622.28K
    - Total Quantity=4809K
 10. October
     - Total Orders=1130K
     - Total Revenue=$301305K
     - Total Profits=$38232.26K
     - Total Quantity=4088K 
11. November
    - Total Orders=1528K
    - Total Revenue=$357754K
    - Total Profits=$56021.81K
    - Total Quantity=5400K
12. December
    - Total Orders=1549K
    - Total Revenue=$409173K
    - Total Profits=$47287.82K
    - Total Quantity=5471K
# SQL query for this :
    SELECT MONTH(Date)Month_Numbers,

    DATENAME(MONTH,Date)Month_Name,

    COUNT(order_id)Total_Orders,

    SUM(Revenue)Total_Revenue,

    CAST(SUM(profit) AS DECIMAL(10,2)) Total_Profit,

    SUM(quantity)Total_Quantity

    FROM SuperStore_Sales_Marketing

    GROUP BY MONTH(Date),DATENAME(MONTH,Date)

    ORDER BY MONTH(Date) ASC


# OUTPUT
![Monthly trends img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/21120526-9b09-4e13-aa79-6d8d98e8cb67)

# Top 10 Sub categories With Highest Income Contributions.
Calaculation Breakdown

Top Sub Category=High Income Growth Contributions
1. Copiers
   - Total Orders=523K
   - Total Revenue=$357511K
   - Total Profits=$63648.11K
   - Total Quantity=1744K
2. Phones
   - Total Orders=804K
   - Total Revenue=$421026K
   - Total Profits=$63127.32K
   - Total Quantity=2841K
3. Bookcases
   - Total Orders=556K
   - Total Revenue=$326560K
   - Total Profits=$38148.80K
   - Total Quantity=1850K
4. Chairs
   - Total Orders=879K
   - Total Revenue=$388185K
   - Total Profits=$34111.34K
   - Total Quantity=3202K

5. Accessories
   - Total Orders=693K
   - Total Revenue=$165781K
   - Total profits=$31521.43K
   - Total Quantity=2465K

6. Appliances
   - Total Orders=399K
   - Total Revenue=$218753K
   - Total Profits=$29381.39K
   - Total Quantity=1412K
7. Storage
   - Total Orders=1235K
   - Total Revenue=$259789K
   - Total Profits=$27522.24K
   - Total Quantity=4017K
8. Machines
   - Total Orders=335k
   - Total Revenue=$178511K
   - Total Profits=$15553.62K
   - Total Quantity=1148K

9. Binders
    - Total Orders=1418K
    - Total Revenue=$107006K
    - Total Profits=$14845.57K
    - Total Quantity=4824K
10. Paper
    - Total Orders=855K
    - Total Revenue=$59671K
    - Total Profits=$14218.62K
    - Total Quantity=3128K

# SQL query for this :
    SELECT TOP 10 Sub_Category,

    COUNT(order_id)Total_Orders,

    SUM(Revenue)Total_Revenue,

    CAST(SUM(profit) AS DECIMAL(10,2)) Total_Profit,

    SUM(quantity)Total_Quantity

    FROM SuperStore_Sales_Marketing

    GROUP BY Sub_Category

    ORDER BY Total_Profit DESC

# OUTPUT

![Top sub categories img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/892596d6-a057-4ba3-8d57-4f2e4499b76e)

# Top 5 Region With Highest Income Contributions.
Calculation Breakdown

Top Region=High income Growth Contributions
1. Central
   - Total Orders=2471K
   - Total Revenue=$633321K
   - Total Profits=$75773.51K
   - Total Quantity=9364k
2. North
   - Total Orders=1159K
   - Total Revenue=$319473K
   - Total Profits=$51540.79K
   - Total Quantity=4334K
3. North Asia
   - Total Orders=575K
   - Total Revenue=$200278K
   - Total Profits=$34587.48K
   - Total Quantity=2086K
4. Central Asia
   - Total Orders=512K
   - Total Revenue=$186116k
   - Total Profits=$29105.77K
   - Total Quantity=1919k
5. Oceania
   - Total Orders=850K
   - Total Revenue=$276134K
   - Total Profits=$29048.79k
   - Total Quantity=3081K
# SQL query for this :
    SELECT TOP 5 Region,

    COUNT(order_id)Total_Orders,

    SUM(Revenue)Total_Revenue,

    CAST(SUM(profit) AS DECIMAL(10,2)) Total_Profit,

    SUM(quantity)Total_Quantity

    FROM SuperStore_Sales_Marketing

    GROUP BY Region

    ORDER BY Total_Profit DESC
# OUTPUT

![Top Region growth img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/b6e40179-4790-42a5-9bd0-c83451f4099b)

# Income  Growth Contributions Per @ Market
Calculation Breakdown=

Top Market=High Income Growth

1. APAC
   - Total Orders=2654K
   - Total Revenue=$881169K
   - Total Profits=$105036.18K
   - Total Quantity=9831K
2. EU
   - Total Orders=2106K
   - Total Revenue=$624205K
   - Total Profits=$70071.61K
   - Total Quantity=7851K
3. LATAM
   - Total Orders=2549K
   - Total Revenue=$560540K
   - Total Profits=$66530.35K
   - Total Quantity=9718K
 4. US
    - Total Orders=2523K
    - Total Revenue=$527467K
    - Total Profits=$63423.96K
    - Total Quantity=9622K 
5. Africa
   - Total Orders=1096K
   - Total Revenue=$191557K
   - Total Profits=$27319.92k
   - Total Quantity=2413K
6. EMEA
   - Total Orders=1219K
   - Total Revenue=$194695K
   - Total Profits=$14991.01K
   - Total Quantity=2758K
7. Canada
   - Total Orders=110K
   - Total Revenue=$13103k
   - Total Profits=$3200.76K
   - Total Quantity=221K

# SQL query for this :
    SELECT Market,

    COUNT(order_id)Total_Orders,

    SUM(Revenue)Total_Revenue,

    CAST(SUM(profit) AS DECIMAL(10,2)) Total_Profit,

    SUM(quantity)Total_Quantity

    FROM SuperStore_Sales_Marketing

    GROUP BY Market

    ORDER BY Total_Profit DESC

# OUTPUT

![Market growth img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/87dc5b4c-66e5-4e34-b5b2-561efcd8922c)


# Top States With Lowest Income Growth  Contributions
Calculation Breakdown

Low State=Low Income Growth
1. Lagos
   - Total Orders=66K
   - Total Revenue=$4363K
   - Total Profits=$-6746.50K
   - Total Quantity=145K
2. Illinois
   - Total Orders=153K
   - Total Revenue=$28701K
   - Total Profits=$-6582.30K
   - Total Quantity=635K
3. Istanbul
   - Total Orders=89K
   - Total Revenue=$7522K
   - Total Profits=$-6432.10K
   - Total Quantity=213K
4. Stockholm
   - Total Orders=40K
   - Total Revenue=$5936K
   - Total Profits=$-3766.61K
   - Total Quanity=151K
5. Lisboa
   - Total Orders=13K
   - Total Revenue=$4747K
   - Total Profits=$-3671.30K
   - Total Quantity=52K

# SQL query for this :
    SELECT TOP 5 State,

    COUNT(order_id)Total_Orders,

    SUM(Revenue)Total_Revenue,

    CAST(SUM(profit) AS DECIMAL(10,2)) Total_Profit,

    SUM(quantity)Total_Quantity

    FROM SuperStore_Sales_Marketing

    GROUP BY State

    ORDER BY Total_Profit ASC

# OUTPUT

![Lowest States growth img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/42eae5df-2a1a-4e8d-9d15-f842da3eb48d)

# Top Customers With Lowest Income Growth Contributions
Calculation Breakdown

Low Customer=Lowest Income Growth

1. Henry Goldwyn
   - Total Orders=21K
   - Total Revenue=$6214K
   - Total Profits=$-3435.69K
   - Total Quantity=70K
2. Saphhira Shifley
   - Total Orders=22K
   - Total Revenue=$8978K
   - Total Profits=$-1841.31K
   - Total Quantity=98K
3. Nancy Lomonaco
   - Total Orders=17K
   - Total Revenue=$3047K
   - Total Profits=$-1581.19K
   - Total Quantity=57K
4. Benjamin Farhat
   - Total Orders=15K
   - Total Revenue=$3541K
   - Total Profits=$-1578.86K
   - Total Quantity=59K
5. Stefania Perrino
   - Total Orders=19K
   - Total Revenue=$3979K
   - Total Profits=$-1532.25K
   - Total Quantity=70K

# SQL query for this :
    SELECT TOP 5 Customer_Name,

    COUNT(Order_Id)Total_Orders,

    SUM(Revenue)Total_Revenue,

    CAST(SUM(Profit) AS DECIMAL(10,2) )Total_Profit,

    SUM(Quantity)Total_Quantity

    FROM SuperStore_Sales_Marketing

    GROUP BY Customer_Name

    ORDER BY Total_Profit ASC

# OUTPUT

![Lowest Customers Growth IMG](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/c2c8552b-9b62-4d68-bb5b-517dc7940d27)

# Top Sub Categories With Lowest Income Growth
Calaculation Breakdown

Low Sub category=Lowest Income Growth

1. Tables
   - Total Orders=244K
   - Total Revenue=$208139K
   - Total Profits=$-20637.02K
   - Total Quantity=828K
2. Fasteners
   - Total Orders=586K
   - Total Revenue=$20655K
   - Total Profits=$3127.39K
   - Total Quantity=2048K
3. Labels
   - Total Orders=645K
   - Total Revenue=$17858K
   - Total Profits=$3548.13K
   - Total Quantity=2335K
4. Supplies
   - Total Orders=546K
   - Total Revenue=$50549K
   - Total Profits=$4917.93K
   - Total Quantity=1934K
5. Envelopes
   - Total Orders=563K
   - Total Revenue=$37505K
   - Total Profits=$6284.33k
   - Total Quantity=1926K

# SQL query for this :
    SELECT TOP 5 Sub_Category,

    COUNT(Order_Id)Total_Orders,

    SUM(Revenue)Total_Revenue,

    CAST(SUM(Profit) AS DECIMAL(10,2) )Total_Profit,

    SUM(Quantity)Total_Quantity

    FROM SuperStore_Sales_Marketing

    GROUP BY Sub_Category

    ORDER BY Total_Profit ASC

# OUTPUT

![Lowest sub categories img](https://github.com/kipngetichs/Super-Store-Project/assets/169267198/f9038afc-c50c-4783-b7f6-af10516deb69)

# Discovery
- What I Have Learned
- I Discovered That:
1. England,New York,California,New South Wales and San Salvador are among the states that contributes to High Income Growth in SuperStore Sales Marketing.
2. Adrian Barton,Hunter Lopez,Mike Gockenbach,Cynthia Arntzen and Denny Joy are among the customers that contributes to High Income Growth in SuperStore Sales Marketing.
3. Office Supplies and Furniture are among the categories that are highly ordered compared to Technology which contributes to the highest profits in all categories.
4. Standard Class and Second Class are among the ship modes with high populariry also contributes to High Income Growth Compared to First Class and Same Day which are low in popularity and also low income contributions.
5. From Month of January to May There is slightly low income growth than from Month of June to December where High Income growth is experienced more.
6. Copiers,Phones,Bookcases,Chairs,Accessories,Appliances,Storage,Machines,Binders and Paper are among the sub categories with high income growth contributions to superstore sales marketing.
7. Central,North,North Asia,Central Asia and Oceania are among the regions with highest income growth contributions in superstore marketing sales.
8. APAC,EU,LATAM and US are among the Markets that contributes to high income growth compared to Africa,EMEA and Canada which have low income contributions in Superstore sales.
9. Lagos,Illinois,Istanbul,Stockholm and Lisboa are among the states that contributes to the lowest income growth in superstore sales.
10. Henry Goldwyn,Saphhira Shifley,Nancy Lomonaco,Benjamin Farhat and Stefania Perrino are among the customers that contributes to lowest income growth in superstore sales marketing.
11. Tables,Fasteners,Labels,Supplies and Envelopes are among sub categories that contributes to lowest income growth in superstore sales marketing.
# Recommendations 
Here is the recommendations based on the insights gathered :
1. Targeting High-Performing Regions ,Markets and Customers:
 - Regional Focus:

   1. Investing in High-Income Regions:Increasing marketing and sales efforts in England, New York, California, New South Wales, and San Salvador States by considering region-specific promotions and localized marketing campaigns will be the best strategy to maintain and even higher income growth.
   2. Leveraging Best Practices: Applying successful strategies from high-income regions to improve performance in lower-performing areas like Lagos, Illinois, Istanbul, Stockholm, and Lisboa
- Customer Prioritization:
  1. High-Value of  Customers: Offering personalized experiences, loyalty programs, and exclusive offers to top customers like Adrian Barton, Hunter Lopez, Mike Gockenbach, Cynthia Arntzen, and Denny Joy will be the best strategy to maintain and even high income growth consistencies.
  2. Retention Strategies: Developing retention strategies for low-performing customers such as Henry Goldwyn, Saphhira Shifley, Nancy Lomonaco, Benjamin Farhat, and Stefania Perrino by understanding their needs and addressing any pain points will be the best solution for this.
2. Product and Category Management:
- Optimize Product Mix:
     1. Focusing on High-Profit Categories: While Office Supplies and Furniture are highly ordered, Technology contributes the highest profits. Increasing inventory and marketing focusing on profitable Technology items will be the best ideal solution for this.
     2. Promotion of High-Growth Subcategories: Prioritizing marketing efforts for subcategories like Copiers, Phones, Bookcases, Chairs, Accessories, Appliances, Storage, Machines, Binders, and Paper will be the best strategy for this.
- Renewing Low-Performing Subcategories:
  1. Investigating and Improving: Analyzing why Tables, Fasteners, Labels, Supplies, and Envelopes have low income growth by  considering making substantial modifications to product offerings or repositioning these items will be the best solution if we need high income from these sub categories.
3.  Shipping and Logistics Optimization:
   - Popular Ship Modes:
     1. Enhancing Standard and Second Class Shipping: Since these are the most popular and contribute significantly to income, ensuring they are cost-effective and efficient will be the best idea for this and possibly offering additional benefits for these shipping modes also needed.
  - Improving Low-Performing Shipping Options:
    1. Analyzing First Class and Same Day Shipping: Identifying reasons for their low popularity and income contribution. Considering cost reduction strategies or adding value to make these options more attractive will be best ideal solutions if we want high income contributions.
4. Seasonal and Temporal Strategies:
- Seasonal Marketing:
    1. Boosting Off-Season Sales: Developing strategies to increase sales from January to May. Considering seasonal promotions, discounts, and marketing campaigns targeting this period will be the best solutions if we want high income within this period.
   2. Maximizing Peak Season: Capitalizing on high-income growth from June to December with intensive marketing campaigns and promotions to maximize revenue during this period will be the best idea.
5. Regional and Market-Specific Strategies:
- High-Income Regions:
    1. Regional Customization: Customizing marketing and product strategies for Central, North, North Asia, Central Asia, and Oceania regions to maximize high income growth will be best idea.
- Market Prioritization:
   1. Focusing on APAC, EU, LATAM, and US: Given their high income contributions, tailoring marketing campaigns to the specific preferences and trends in these markets will be the best ideal to do.
   2. Exploring Growth Opportunities: Investigating potential barriers in Africa, EMEA, and Canada to understand low contributions and explore opportunities for growth will be the best solution to improve this markets.

# Potential ROI
ROI we expect when we take this action:
# ROI For Targeting High-Performing Regions and Customers
- Regional Focus:
  1. Revenue Increase: 15-20% increase in sales in high-income regions.
  2. Cost Increase: 10-12% for marketing and operational adjustments.
  3. ROI Calculation:

         (20% Revenue Increase-12% Cost Increase)/12% Cost Increase=67%

- Customer Prioritization:
  1. Revenue Increase: 10-15% increase from high-value customers.
  2. Cost Increase: 5-8% for loyalty programs and retention strategies.
  3. ROI Calculation:
  
         ( 15% Revenue Increase-8% Cost Increase)/8% Cost Increase=88%
# ROI For Product and Category Management
- Optimize Product Mix:
  1. Revenue Increase: 20-25% increase in high-profit categories.
  2. Cost Increase: 10-15% for increased inventory and marketing efforts.
  3. ROI Calculation:

         (25% Revenue Increase-15% Cost Increase)/15% Cost Increase=67%
 - Renewing Low-Performing Sub categories:
   1. Revenue Increase: 10-15% increase from improved subcategories.
   2. Cost Increase: 5-8% for product development and repositioning.
   3. ROI Calculation:
  
          (15% Revenue Increase-8% Cost Increase)/8% Cost Increase=88%    
# ROI For Shipping and Logistics Optimization
- Popular Ship Modes:
  1. Revenue Increase: 10-15% increase from popular shipping options.
  2. Cost Increase: 5-7% for enhancing shipping services.
  3. ROI Calculation:
 
         (15% Revenue Increase-7% Cost Increase)/7% Cost Increase=114%
- Improving Low-Performing Shipping Options:
  1. Revenue Increase: 5-10% increase from improved shipping options.
  2. Cost Increase: 3-5% for analyzing and improving services
  3. ROI Calculation:
 
         (10% Revenue Increase-5% Revenue Increase)/5% Revenue Increase=100%

- Seasonal Marketing:
  1. Revenue Increase: 10-15% increase during off-peak months, 15-20% during peak months.
  2. Cost Increase: 5-10% for marketing and promotional efforts.
  3. ROI Calculation:
 
         (20% Revenue Increase-10% Cost Increase)/10% Cost Increase=100%

ROI For  Regional and Market-Specific Strategies
- High-Income Regions:
  1. Revenue Increase: 15-20% increase in these regions.
  2. Cost Increase: 10-12% for customized marketing and products.
  3. ROI Calculation:

         (20% Revenue Increase-12% Cost Increase)/12% Cost Increase=67%
- Market Prioritization:
  1. Revenue Increase: 10-15% increase from prioritized markets.
  2. Cost Increase: 7-10% for market research and tailored campaigns.
  3. ROI Calculation:
 
         (15% Revenue Increase-10% Cost Increase)/10% Cost Increase=50%
# Potential Courses of Actions
# Action plan
Actions need to be taken is as follows:
# Action For Targeting High-Performing Regions and Customers
- Regional Focus:
  1. Investing in High-Income Regions: Developing region-specific promotions and marketing campaigns targeting England, New York, California, New South Wales, and San Salvador.
  2. Leveraging Best Practices: Implementing strategies from high-performing regions in lower-performing areas like Lagos, Illinois, Istanbul, Stockholm, and Lisboa.

- Customer Prioritization:
  1. High-Value Of Customers: Creating personalized experiences and exclusive offers for top customers.
  2. Retention Strategies: Developing and implementing strategies to address the needs and improving the satisfaction of low-performing customers.

# Action For Product and Category Management
- Optimize Product Mix:
  1. Focus on High-Profit Categories: Increasing inventory and marketing focus on profitable Technology items.
  2. Promotion of High-Growth Subcategories: Prioritizing marketing efforts for subcategories like Copiers, Phones, Bookcases, Chairs, Accessories, Appliances, Storage, Machines, Binders, and Paper.
- Renew Of Low-Performing Subcategories:
  1. Investigating and Improve: Analyzing and adjusting product offerings for Tables, Fasteners, Labels, Supplies, and Envelopes.
# Action For  Shipping and Logistics Optimization
- Popular Ship Modes:
  1. Enhancing Standard and Second Class Shipping: Ensuring these modes are cost-effective and possibly offer additional benefits.
- Improving Low-Performing Shipping Options:
  1. Analyzing and Improve: Identifying reasons for low popularity and improve First Class and Same Day shipping options.

# Action For Seasonal and Temporal Strategies
- Seasonal Marketing:
  1. Boosting Off-Season Sales: Developing strategies for increasing sales from January to May.
  2. Maximizing Peak Season: Capitalizing on high-income growth from June to December with intensive marketing campaigns.

# Action For Regional and Market-Specific Strategies
- High-Income Regions:
1. Regional Customization: Tailor marketing and product strategies for Central, North, North Asia, Central Asia, and Oceania regions.
- Market Prioritization:
  1.Focusing on APAC, EU, LATAM, and US: Tailoring marketing campaigns to these markets.
  2. Exploring Growth Opportunities: Investigating barriers and opportunities in Africa, EMEA, and Canada.

# Conclusion
- High-Income Growth Regions:
  - Top Contributors: Regions such as England, New York, California, New South Wales, and San Salvador are significant drivers of high income growth. These areas should be the focus of increased marketing and sales efforts, utilizing region-specific promotions and localized campaigns to leverage their potential further.
- High-Value Customers:
  - Top Contributors: Customers like Adrian Barton, Hunter Lopez, Mike Gockenbach, Cynthia Arntzen, and Denny Joy contribute significantly to high income growth. Personalized experiences, loyalty programs, and exclusive offers should be prioritized for these high-value customers to enhance their satisfaction and retention.
- Product Categories:
  - Highly Ordered: Office Supplies and Furniture are the most ordered categories, while Technology contributes the highest profits. Increasing inventory and marketing focus on profitable Technology items can optimize the product mix.
  - High-Growth Subcategories: Items such as Copiers, Phones, Bookcases, Chairs, Accessories, Appliances, Storage, Machines, Binders, and Paper have notable income growth contributions and should be prioritized in marketing efforts.
- Shipping Modes:
  - Popular Options: Standard Class and Second Class shipping modes are popular and significantly contribute to income growth. Ensuring these modes are cost-effective and efficient can sustain their popularity.
  - Improving Low-Performing Options: First Class and Same Day shipping are less popular and contribute less to income. Analyzing and improving these options could attract more customers and enhance their contributions.
- Seasonal Trends:
  - Income Growth: From January to May, income growth is slightly lower, whereas from June to December, higher income growth is observed. Developing strategies to boost off-season sales with seasonal promotions and intensive marketing during peak seasons can optimize revenue throughout the year.
- Regional Contributions:
  - High-Growth Regions: Central, North, North Asia, Central Asia, and Oceania regions show the highest income growth contributions. Customizing marketing and product strategies for these regions can maximize growth.
  - Market Focus: APAC, EU, LATAM, and the US are leading markets in terms of income contributions. Tailoring marketing campaigns to these regions' specific preferences and trends can further enhance growth.
- Low-Performing Areas:
  - Regions: Lagos, Illinois, Istanbul, Stockholm, and Lisboa are among the regions contributing to the lowest income growth. Applying successful strategies from high-income regions and investigating potential barriers in these areas could improve their performance.
  - Customers: Henry Goldwyn, Saphhira Shifley, Nancy Lomonaco, Benjamin Farhat, and Stefania Perrino are customers with the lowest income growth contributions. Understanding their needs and addressing any pain points can help in developing retention strategies.
- Low-Growth Subcategories:
  - Subcategories: Tables, Fasteners, Labels, Supplies, and Envelopes have low income growth contributions. Investigating the reasons behind their performance and considering product improvements or repositioning these items could revitalize their growth.

     
