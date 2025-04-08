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

![image_alt]()

• Name it 'Dimesions'.Click 'OK'. Now place all the dim tables under this group by drag and drop.

![image_alt]() 

• Use the same approach for creating 'Facts' Group. And place all fact tables under this group by drag and drop.

![image_alt]()

# Create a Separate Date Table 

• New Source ➜ Blank Query

![image_alt]()

• 

![image_alt]()

•

![image_alt]()

• 

![image_alt]()

 ![image_alt]()

 ![image_alt]()

 ![image_alt]()

 ![image_alt]()

 ![image_alt]()



