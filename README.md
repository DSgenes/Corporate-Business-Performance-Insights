# Corporate-Business-Performance-Insights

# Problem Statement

  This is a project-based learning course. We will use an imaginary company called AtliQ Hardware and discuss its business model. 
  It is a consumer goods electronics company having operations in various countries. Their business is growing rapidly and they
  still rely on excel files for data analytics. Excel files are hard to consume and not effective in generating insights. Also
  due to the lack of effective analytics the company faced a major loss in Latin America.

  Senior executives of this company have decided to invest in a data analytics project and have assigned a team for this work.

# Tasks : 
# Finance View : 
  Show Profit and loss statement to understand financial performance across Markets, Products, Customers etc.

# Sales View : 
  Show Top/Bottom Customers along with Key Metrics. A matrix would be preferable to understand their performance 

# Marketing View :
  Same as Sales View but for Products

# Supply Chain :
  Reliability, Forecast Accuracy in a view to understand SC Performance

# Executive View :
  Integrated view of key insights for executives. (More details TBD)

--------------------------------------------------------------------------------------------------------------------------------

# Step 1 : Data Collection and Preparation

# Data Source : MySQL Database

# Database : gdb041                                             
# Tables   : 
            • dim_customer                                                                   
            • dim_market                                    
            • dim_product                                   
            • fact_forecast_monthly                         
            • fact_sales_monthly                            

# Database : gdb056
# Tables   :
            • frieght_cost
            • gross_price
            • manufacturing_cost
            • post_invoice_deductions
            • pre_invoice_deductions
            
• Get Data from another source ➜ MySQL Database ➜ Enter Your Server and Database Name ➜ gdb041 (Database Name) ➜ OK

# Step 2 : Data Exploration and Analysis

# Transformations in Power Query Editor

# Grouping Data :

• Grouping data into dimension and fact tables and place the dim tables under Dimesions group and  facts tables under Facts. 

• Right Click on any of table ➜ Move to Group ➜ New Group

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/3c44542504e6706e010a242bca62271e2b5408d3/Screenshot%201.png)

• Name it 'Dimesions'.Click 'OK'. Now place all the dim tables under this group by drag and drop.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/3c44542504e6706e010a242bca62271e2b5408d3/Screenshot%202.png) 

• Use the same approach for creating 'Facts' Group. And place all fact tables under this group by drag and drop.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/3c44542504e6706e010a242bca62271e2b5408d3/Screenshot%203.png)

# Create a Separate Date Table 

• New Source ➜ Blank Query

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/3c44542504e6706e010a242bca62271e2b5408d3/Screenshot%204.png)

• If you look at our fact_sales_monthly table , you'll see all our dates start from 1st September, 2017 till December 2022 ends.

• Write this code and you'll see the nice dates coming in.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/656ca0bf38603646d0b3ac0523e8a91bcf4be554/Screenshot%205.png)

• To convert this list into date table.

• Selecting the 'List' Column ➜ To Table ➜ OK

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/656ca0bf38603646d0b3ac0523e8a91bcf4be554/Screenshot%206.png)

![image_alt]()

• It'll become 'Column1' to 'List'.

• Right Click on 'Column1' ➜ Change Type ➜ Date

• Rename Query to dim_date table. And Column1 to date.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/656ca0bf38603646d0b3ac0523e8a91bcf4be554/Screenshot%207.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/3277566dcc5d0d1b869011405cf2a400e8bbe487/Screenshot%208.png)

• Add a 'New Column' as 'Start of Month' Column.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/0f4388ce76a37a600a4a72b7278aef7cf6b14d92/Screenshot%209.png)

• Rename the column from 'Start of Month' to 'Month'. 

# Create a 'Fiscal Year' Column

• Fiscal year starts in 'September 2017'. Create a 'Custom Column'.Extract the year out of month column.

• Custom Column ➜ fiscal_year ➜ Add 'Date.Year' function ➜ Insert 'month' ➜ OK

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/efb5216dcd712c8469d1b9baf92967b891333afd/Screenshot%2010.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/5c90ae3b6ef56b422c2478611f792cd15e590d22/Screenshot%2011.png)

• Now, make the fiscal year such that when its September 2017 I want it to be 2018 because that's when the new , the first month of the fiscal year 
  starts. Re-evaluate the formula. Add 4 months because Sep, Oct, Nov, Dec after these 4 months the next year starts.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/2eb2931f34dfab783622a5aafaaa81460f4e9486/Screenshot%2012.png)

• Change the fiscal_year column datatype to 'Text'.

• Close & Apply and Save all the changes.

# Data Validation 

# Problem Statement:

  Peter(Junior Data Analyst), working under Tony’s (Manager) guidance, is tasked with ensuring the accuracy and validity of the sales database against predefined
  benchmark figures for the fiscal year 2018. As part of this process, Peter must verify that the data used in the Power BI analysis
  aligns with the benchmark sales numbers, particularly focusing on the 2018 total sales quantity of 3.45 million units. This involves:

# 1. Validating Data:

  Verifying that the sales database is accurate and consistent with the benchmark figures provided by Nick 
  (the product owner).

# 2. Building Visuals: 

  Creating Power BI visuals that clearly display and validate sales data in relation to these benchmark numbers.

# 3. Fiscal Year Focus: 

  Ensuring that all analysis is done in the context of the fiscal year, specifically aligning the data against the 
  fiscal year structure for more accurate insights.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/38dc025e5d8bb064aa37292942ec89eb51513cdc/Screenshot%2014.png)

# First Verify the Value for Product Sold in Power BI

• Calculate the distinct product code sold during that year.

• Its mentioned in the Data log as 345 in Year 2022.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/098840095eeaffdf67242535792ad309ad04a192/Screenshot%2015.png)

• Now, I want to know about the active customers with whom we did a business in Year 2022.In the Data log its mentioned as 209.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/a56c913c5f8f98a9d4d75d60f707da25f618fa4e/Screenshot%2016.png)

![image_alt]()

![image_alt]()




