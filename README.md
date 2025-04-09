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

• So in 2022 AtliQ sold the hardware to 27 different Markets.As it's mentioned in th Data log.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/4726230baf03568ef08f4ce68845f9297b3ba263/Screenshot%2017.png)

• Now verifying Sales Quantity and Forecast Quantity. The problem we encounter is that the forecast quantity for 2022 is 86447417 but the 
  Benchmark that we're given is 86.82346 M in the data log provided by the product owner. So the data, the quantity we are getting in
  Power BI is actually less than the benchmark numbers that are given to us. So now, the Peter, the data analyst will reach out to 
  servicing who is a data engineer. They'll communicate on Teams chat and try to figure out the issue. After checking this out, 
  there's a new product launch after GPM etc. After fixing this gap the ratio will be matched with the provided data log.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/51ebbf530bdff7c57eed9edb3b35fd7a24049959/Screenshot%2018.png)

# Building a Table mixed with Actuals and Forecasts Values

# Automation in Power BI

# First Find the Current Month

• One way of getting current month would be get the last date in your actual table which is fact_sales_monthly table.

• Create a Reference table for this. 

• Right click on fact_sales_monthly table ➜ Reference 

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/6886699f3349bd201e8a2add35b9be80583e7e1a/Screenshot%2019.png)

• Fetch only the details of dates column.It'll get the date column for month.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/34e8f29b7f90cff7c9a1f1f03ee315a00238faa7/Screenshot%2020.png)

• By writing this code you'll get your actual sales current month. Basically this is the date till which you have your 
  actual sales data available. Double click on this table and rename it as LastSalesMonth.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/f3f14c0fa4c0311bef216d8faaa9b431d33071e0/Screenshot%2021.png)

• Create a Reference table for fact_forecast_monthly. 

  Right click on fact_forecast_monthly ➜ Reference ➜ Rename to 'Remaining Forecast'

• Select any filter on date column to create this formula.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/a5deb53a8e61e896de247093db964104fdb02cfc/Screenshot%2022.png)

• Now I can use this formula and say my date should be greater than LastSalesMonth. My LastSalesMonth was 01/12/2021. 
  Do the sort ascending to see the dates starts from after that.So it is starting from 1st of January, 2022.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/f61d693ab5ef71991668e6f227bae12ac59f9c5b/Screenshot%2023.png)

• Create a new third table. And combined fact_sales_monthly and Remaining Forecast together by using Append Queries as New.

  Click on Append Queries ➜ Append Queries as New ➜ Name it as 'FactActualsEstimates'

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/b607bae4a90250f4722e47322c50aeec1ef91d31/Screenshot%2024.png)

• Column 'sold_quantity' is available for all my actual dates and forecast_quantity is available for all my future dates. I want sold_quantity
  and forecast_quantity under one column.

      • Go to Remaining Forecast table ➜ Rename column forecast_quantity to Qty 
      • Go to fact_sales_monthly table ➜ Rename column sold_quantity to Qty
      • Rename FactActualsEstimates ➜ fact_actuals_estimates
      
  Now when you go to your FactActualsEstimates Table your forecast_quantity and sold_quantity column's values will be
  placed under one column as Qty.

• Move frieght_cost, gross_price, manufacturing_cost, post_invoice_deductions, pre_invoice_deductions, Remaining Forecast,
  fact_actuals_estimates into a New Group called 'Supporting Facts'.

# Create a Custom Column 'fiscal_year' 

• Adding fiscal_year in our fact_actuals_estimates table as this table didnt have a fiscal year.Use the same approach as above
  by using a 'Custom Column' approach for fiscal_year column. Change its Data Type to be 'Text'.

# Merging Queries for Two Tables

• So, this is my final table fact_actuals_estimates which is going to be used among all my visualizations. 
  So I need to merge gross_price table and fact_actuals_estimates table with thses two columns product_code
  and fiscal_year.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/b956a1c25b65d113dd5c9cda6c96c9f5586edc72/Screenshot%2025.png)

• You can just ignore privacy levels. Because you're working from your local computer but if you're working from an organization
  then select it as Organizational by deselecting Ignore Privacy Level, etc.
  
![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/a3948aeb2069035a681d3adc57ff48f57e53c806/Screenshot%2026.png)

• After Merging the queries, a column will be created like this.Here, it join it with the whole table.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/62ba5273786b8d34d1d61e0bd57ff25b1b0fdcf2/Screenshot%2027.png)

• To expand the table, what we need to do is select this icon and just select the gross_price column to expand it.
  And you'll see it'll only fetch the values for gross_price column. Fix its data type to 'Fixed Decimal Number $'.
  So this gross_price column contains the price of one item in that fiscal year but you're selling multiple.
  So if you look at Qty column if youre selling 81 for example so your gross price amount would be 81 into 13.20
  in this case.
  
![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/9bb796c23cb23bba583757dd4e40e825b2f57367/Screenshot%2028.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/69b42407a118333a6375ab85a312934c58a34ef4/Screenshot%2029.png)

• Now you'll create another 'Custom Column' for gross_price_amount this is basically total amount.The first one gross_price
  column was the amount for one quantity. This column gross_price_amount contains the  price for multiple quantities.
  Change its data type to 'Fixed Decimal Number'.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/69b42407a118333a6375ab85a312934c58a34ef4/Screenshot%2030.png)

• Use the same approach to join another table pre_invoice_deductions with fact_actuals_estimates table using merge queries.And fix
  its data type to percentage.

• So if you want to change the name of a column like 'gross_price_amount' to 'gross_sales_amount'.Go to the previous steps.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/bb532067e44f6f2a421a4a079e77f979ab9f1b5d/Screenshot%2031.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/ced8cded9e654eebb4895a4356d55bebfdd149d9/Screenshot%2032.png)

• Add a 'Custom Column' for pre_invoice_discount_amount. Change its data type to 'Fixed decimal Number'.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/ed89368b26a0b3c8099bc24d20ad9929c9d8509d/Screenshot%2033.png)

• Add another 'Custom Column' to 'net_invoice_sales_amount'

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/1014d11b36d555f832a9acd1520e4a6c4df56c2d/Screenshot%2034.png)

# Naming query steps

![image_alt]()

• All the steps you've done making this file give it a nice description and rename it. Hover the cursor over it and you'll see 
  the nice description.

  Right Click ➜ Properties 

![image_alt]()



![image_alt]()



