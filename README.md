Business Insight 360 

Situation and Overview:  
Atliq Hardware is a hypothetical fast-growing electronic devices company operating in markets regions like Asia Pacific, European Union, North America, and Latin America. The company wants to expand its business and grow eventually contributing to higher sales and gross margin but facing a major setback in LATAM and NA Markets due to lack of business insights and the growing competition by big tech players. So, board members decided to dive deep into sales data and P&L statements of each market. For that they want to rely on Analytics to draw data driven actionable insights.  

Task: 
Conduct deep analysis and build functional dashboards for different verticals of the business using data from different sources like excel sheets and databases to study over sales trends of each market or country for different products and categories. 
There should be a seperate dashboards for each business vertical like sales, marketing, supply chain, basic P&L statement and one for company executives as well.
Basic Details about Dashboards: 
Finance View: Show Profit and Loss statement to understand financial performance across markets, products and Customers.
Sales View: Show Top/Bottom Customers along with key matrix. 
Marketing View: Same as sales view but for products.
Supply Chain View: Reliability and forecast accuracy across markets and product categories to understand supply chain performance. 
Executive View: Integrated view of key insights for executives to make quick decisions. 

Action and Workflow:
1.	Data gathering: Data is available in different formats; SQL databases and excel sheets. 
Fact and dimension data is available in two databases gdb041 and gdb056. 

GDB041: Database gdb041 contains fact and dimension tables. There are 2 fact tables including fact_sales_monthly, fact_forecast_monthly and 3 dimension tables including dim_customer, dim_market, dim_product.
GDB056 : Database gdb056 contains 5 tables including freight_cost, gross_price, manufacturing_cost, pre_invoice_deduction, and post _invoice_deduction depending upon different markets, countries, products, etc. 

There is some extra data in tables like targets, operational cost, and marketshare, available in excel sheets which will be incorporated later in the data model.



2.	Data Exploration: Getting quick overview of the data to understand basic structure and datatypes of the columns available in different tables in order to make the data model and use it in data wrangling steps.

3.	Data Preprocessing and Cleaning: Preprocessing and cleaning of the data included the following steps:

•	ETL (Extract Transform Load): The data is first loaded into MySQL server and then connected with PowerBi desktop. 
•	Data Transformation: The data is then loaded into Power Query. Removed duplicates where not necessary, dealt with Null Values, assigned proper Datatypes, removed punctuation errors in values where necessary.
•	Data Wrangling: 
Built a dim_date table from fact_sales_monthly table. 
Built the data model to connect tables using snowflake method.
Built sales_actual_estimates table from fact_sales_monthly and fact_forecast_monthly tables to build necessary visuals and DAX measures. 
Merged tables and queries into fact tables with different techniques like merging, appending, and Calculated columns. 
Renamed Columns and tables as per the need.
Disables the unwanted columns.
Put enable off for unwanted tables.

4.	Now, built multi-level visuals using different DAX measures and calculated columns including tables, Matrices, pie charts, line charts, waterfall chart, stacked column and line chart, scatter chart, stacked area chart, KPI cards, etc. 
5.	Used Toggle Buttons to switch between visuals to change the comparing business matrix. Used Action icons to navigate through pages. 
6.	Built many different filters and slicers to learn about any specific Market, Customer, Product, or any FY.
7.	Incorporated Tooltip feature to compare between Gross Margin and Net Sales for any customer.
8.	Finally added aesthetics to all the visuals and pages to make them visually appealing, uniform with respect to each other and easy to understand.

 
Dataset Details:


GDB041 – 
I.	fact_sales_monthly 
Columns: date, division, product_code, category, product, market, platform, channel, customer_code, customer_name, sold_quantity
II.	fact_forecast_monthly
Columns: Same as fact sales monthly
III.	dim_customer
Columns: customer, market, platform, channel, customer_code
IV.	dim_product
Columns: product_code, division, segment, category, product, variant
V.	dim_market
Columns: market, subzone, region


GDB056 – 
I.	freight_cost
Columns: market, fiscal_year, freight_pct, other_cost_pct
II.	gross_price
Columns: product_code, fiscal_year, gross_price
III.	manufacturing_cost
Columns: product_code, cost_year, manufacturing_cost
IV.	pre_invoice_deduction
Columns: customer_code, fiscal_year, pre_invoice_discount_pct
V.	post_invoice_deduction
Columns: customer_code, products_code, date, discount_pct, other_deduction_pct


Excel Sheets –
I.	Operational expenses
Columns: market, fiscal_year, adpromotion_pct, other_operational_expense_pct 
II.	Targets
Columns: market, month, ns_target, np_target, gm_target 
III.	Market share
Columns: subzone, category, fy_desc, total_market_sales_$, atliq_sales_$, dale_ sales_$, innovo_ sales_$, pacer_ sales_$, bp_ sales_$, other_ sales_$.



Results: https://app.powerbi.com/view?r=eyJrIjoiMWM2ODM3ZmItOWY2MS00YzkyLTg4MDItMjQ3Y2M2ZDhiNTUxIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9
