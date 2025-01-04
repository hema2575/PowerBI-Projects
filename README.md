# Ecommerce Sales -Dashboard

### Dashboard Link : Will be provided upon request

## Problem Statement

How is the company's ecommerce sales performing for different different user segments, and what are the KPIs ? 

Well, the answer is this interactive dashboard that is designed to display sales trends and display YTDs by Category, State, Region and Shipping Type dynamically. The dashboard displays 5 top and bottom performing products in the selected category and selected state for the chosen segment. 

There are pie charts that show sales by region and sales by shipping type which also drill down dynamically based on the state chosen.

The dashboard shows that YTD profit margin for consumer has downward trend, while the profit margins are upwards for corporate and homeoffice, providing a clear direction for strategic planning for improvement.  

### Steps followed 

- Step 1 : Import dataset in csv into MS SQL Server.
- Step 2 : Connect PowerBI to MS SQL Server. Open power query editor & load the tables into PowerBI.
- Step 3 : Examine that ecommerce sales data and US latitude and longitude files are loaded 
- Step 4 : Build the KPI Banner to display YTD Sales, Profit, Quantity and Profit Margin. Each of these KPIs will display the dollar amount, a number or a % as appropriate and
           will include a color chaning background, trend icon and a trend line with tool tips to reveal month-wise numbers.
- Step 5 : Create Date Table where the minimum date will be the minimum of order date in the data set and the maximum will be the maximum of order date.  
- Step 6 : Add a column in the Date Table to calculate the number of the month, for example 1 for January, 2 for February and so on. 
- Step 7 : Model the data by creating many-one relationship between customer state to 'name', date in calendar table to order date in the ecommerce sales data
- Step 8 : Add a background to the visualization area and placeholders for the KPI banners
- Step 9 : Create 'new measure' and use TimeIntelligence functions to calculate YTD Sales, YTD Profit, YTD Quantity, YTD Profit Margins      
- Step 10 : Display the calculated KPIs using the 'Card' visual. Use formatting to display the currency or percentage symbols as appropriate. Using 'Area Chart', create a trendline graph to place under the calculated KPI. A filter is applied on this area filter to show values for a year as this is YTD measures. 
- Step 12 : Use conditional formatting to display colors to indicate an upward or downward trend in the KPIs
-YTD Sales = TOTALYTD(sum(ecommerce_data[sales_per_order]),'Calendar'[Date])
-YoY Sales = ([YTD Sales]-[PYTD Sales])/[PYTD Sales]
-PYTD Sales = CALCULATE(sum(ecommerce_data[sales_per_order]), DATESYTD(SAMEPERIODLASTYEAR('Calendar'[Date])))
-Sales Icon = var positive_icon = UNICHAR(9650)
              var negative_icon = UNICHAR(9660)
                var result = IF([YoY Sales]>0, positive_icon, negative_icon)
                return result
-Sales Color = IF([YoY Sales]>0, "Green", "Red")


- Step 13 : Apply a slicer based on Category for the display of dynamic values based on the category of products
- Step 14 : Apply a slicer based on State for the display of dynamic values based on the State of sale
- Step 15 : Use piecharts to show sales by region and sales by shipping type
- Step 16 : Apply slicer to show the differnt segments of users - consumer, corporate and homeoffice.
- Step 17 : The report can now be published to Power BI Service.
  ![ecommDash_readmeimage](https://github.com/user-attachments/assets/e2cd6439-1cb1-4209-a09e-0c6c711818a7)
 
 

# Insights (WIP)


### [1]            
### [2] 
### [3] 
### [4] Some other insights
 
 


