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

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/56bc0e0f4404ac03dfcff2a9bc19737cedf4473d/Screenshot%2035.png)

• All the steps you've done making this file give it a nice description and rename it. Hover the cursor over it and you'll see 
  the nice description.

  Right Click ➜ Properties 

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/a8397e99d89bfca838799602fd218e4bd6d5213f/Screenshot%2036.png)

# Disable load for tables that will not be used outside Power Query

• Right Click ➜ Uncheck Enable Load
    
    • LastSalesMonth            
    • Remaining Forecast
    • gross_price
    • pre_invoice_deductions
    
Note : • This will reduce file size and improve performance. Keep table names minimal(remove preceding db name).
       • Disable load for Gross Price and Pre Invoice Discounts as they are already merged inside PQ.
       
![image_alt]()

• You can't merge all the tables in Power Query it'll affect your execution loads. Like gross_price was a table with thousand 
  rows but post_invoice_deductions take a long time to merge as it contains more than million rows. Also, you can't create 
  calculated columns in DAX as it increases the size of your file so you use both approaches to reduce your query 
  execution time.

  Note : It is good to keep the file size as low as possible to improve the performance.
         You can even use a combination of two methods as appropriate.

# Data Modeling

# Disable the Columns 

• Once we establish the star schema relationships, we'll be able to look up for the customer information product_id information
  from the Dimension table.So, its okay if you remove these columns from your fact_sales_monthly table.

  Go to the Power Query ➜ Select fact_sales_monthly table ➜ Home ➜ Choose Columns ➜ Deselect the unnecessary columns.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/425ac3f2f6a7b7993d96b951d51e59cc343e4e0c/Screenshot%2037.png)

• Use the same approach for fact_forecast_monthly table.

  Go to the Power Query ➜ Select fact_forecast_monthly table ➜ Home ➜ Choose Columns ➜ Deselect the unnecessary columns.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/cc9bee71f8b7f05897c2f302ce2081425a523ba5/Screenshot%2038.png)

# Snow Flake Schema

• Establish connections between tables in the Data Modeling view. Place all the facts tables in center and surround the dim tables
  besides facts tables.The approach we're going to use here is known as 'Snow Flake Schema'. Create connetions between dim and fact
  tables by drag and drop the same columns among both.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/6350b39f62f341425e36c29c59c335e03859e32e/Screenshot%2041.png)
  
![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/dfb415ab21aa46d70a3fa8b904ea61b12996f776/Screenshot%2042.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/d81f90f71768b5f7859b5b7e1e1bc932d64badd4/Screenshot%2039.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/6a8adf95b539d1759a72cb27fc59b56cd3d044ce/Screenshot%2040.png)

• Many-to-many relationships can complicate data management and lead to redundancy, making it difficult to ensure data integrity. It's better
  to use a junction table to simplify the structure into One-to-Many relationships.

• The entities which contains Many-to-Many relationships will drop an error message. For this you have to create another dim table.
  This table will generate new connetions between One-to-Many relationships.
  
  Go to the Report View ➜ Modeling ➜ New table

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/87d21b358f49f682eed4a656e3fef93674867521/Screenshot%2043.png)

• In the Table View, you'll see the table we created fiscal_year.And this table has only unique rows.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/44f5b08abe9e5474e96c6de087849e79a2027544/Screenshot%2044.png)

• Generate new connections between tables.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/a47578b8d9448568e373462873425fed00d8e488/Screenshot%2046.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/609670c26b731579ae3101c58ffe2b57c666f7ce/Screenshot%2045.png)

# Aggregating Columns

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/e8818310422cac7531f03447f0b7a81eb22d1346/Screenshot%2056.png)

• Now aggregating a column post_invoice_deductions_amount in fact_actuals_estimates table. Use discounts_pct column from the post_invoice_deductions
  table. Format this column as 'Currency'.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/8414c2d6e5a9e590e8179049dcca3cae6404c381/Screenshot%2047.png)

• Create another column in fact_actuals_estimates table using the same approach.Format this column as 'Currency'.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/eab4eb4285d34b94f7b897ababb352c9738e14b3/Screenshot%2048.png)

• Create net_sales_amount column in fact_actuals_estimates.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/758d68feb353078b2a21081d2c8cc16f6ad44c67/Screenshot%2049.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/15fcee4a01ad595c49eb16e9a5907e6986d095f2/Screenshot%2057.png)

• Create manufacturing_cost column in fact_actuals_estimates.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/4fc943d47ccabb06c09fdeb8a85a103b84d10975/Screenshot%2050.png)

• Create frieght_cost column in fact_actuals_estimates.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/5694b21822473c0cfa7f46aa2fe0d402fa6df78d/Screenshot%2051.png)

• Create other_cost column using in freight_cost in fact_actuals_estimates.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/278c83421a792978c28973bd6789750b430213be/Screenshot%2052.png)

• Create total_cogs_amount column in fact_actuals_estimates.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/bcd59e150faba0f11d102714795f79d524882a2c/Screenshot%2053.png)

• Create a gross_margin_amount column in fact_actuals_estimates.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/1fec2e296c76fd6c17661f606e4556c4ee3c6cb7/Screenshot%2054.png)

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/ec4e2673f72f3d6d33fddc3b1d787893f1e2648e/Screenshot%2059.png)

# Reduce PBIX file size 

• Download the DAX Studio.It has an integration with Power BI. Connect this third-party tool with Power BI and verify
  which of the columns occupying more space.

• Remove unnecessary columns to reduce pbix file size.Because in terms of data you're still connected with MySQL Database,
  and when you need any columns it will dynamically calculate these columns. Forexample if gross_price and pre_invoice_deductions
  columns are occupying more space and after removing them I can still calculate the net_invoice_sales even if its depended on
  these two columns.Because these two columns are still there in your MySQL database and it'll retrieve the results through
  calculations dynamically.

• Go to Power Query Editor and remove gross_price, pre_invoice_discount_pct, pre_invoice_discount_amount.
  Net_invoice_sales column has dependency on those two columns but nothing happened because you're still connected with 
  your database.

• Total_cogs_amount and gross_margin occupying lot of space.Delete them and we can still get it from memory.

---------------------------------------------------------------------------------------------------------------------------------------------
# Finance View 

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/abddaf9a08b0f834f23a6cbed59abcbad4716f56/Screenshot%2060.png)

# Communicating Insights : 

This visual, titled "Actual and Forecast Net Sales by Month" for Fiscal Years, provides a clear time series overview of net sales performance.
Here are the key insights:

# 1. Peak and Trough Sales

# Maximum Sales:

Value: $108.41M

Date: December 2020

Insight: This indicates a strong performance possibly due to seasonal factors like year-end demand or promotions.

# Minimum Sales:

Value: $57.72M

Date: June 2021

Insight: This low could reflect an off-season, operational bottlenecks, or external factors like market shifts or policy changes.

# Average Sales

• The average net sales line is marked at $68.65M, acting as a benchmark.

# Observation:

• Sales exceeded the average in the months leading up to and including Dec 2020.

• Post-Dec 2020, sales dropped and remained below average, indicating a performance dip.

# Trend Analysis

From Sep 2020 to Dec 2020, there's a noticeable uptrend.

A sharp decline follows into early 2021.

Through 2021, the sales plateau, staying relatively stable but consistently under the average.

# Forecast Area

The chart includes a Forecast Sales Area, but it’s faint and likely projects modest growth or stability beyond the displayed timeframe.

# Business Implications:

Dec 2020’s peak might serve as a case study—replicating its drivers could boost future performance.

# Post-peak underperformance signals the need for investigation:

• Were there market changes?

• Was customer behavior different?

• Did marketing efforts drop?

The consistent low trend suggests strategic shifts might be needed to regain momentum.

![image_alt](https://github.com/DSgenes/Corporate-Business-Performance-Insights/blob/a7afced033c95e1f4121771093f450b9a22eaa84/Screenshot%2061.png)

![image_alt]()

