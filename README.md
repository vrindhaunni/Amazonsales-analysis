# Amazon Sales-Dashboard


## Problem Statement

Sales management has emerged as the cornerstone of commercial enterprises, essential for navigating market competition and optimizing distribution channels. To address this, I conducted an in-depth analysis of Amazon sales data to uncover sales trends, identify key metrics, and establish meaningful relationships between attributes.



### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : Clean the data and load it to power bi.
- Step 5 : In the report view, under the view tab, theme was selected.
- Step 6 : Since the data contains various ratings, thus in order to represent ratings, a new visual was added using the three ellipses in the visualizations pane in report view. 
- Step 7 : Visual filters (Slicers) were added for the fields named "Country", "Priority", "Year" .
- Step 8 : The card visuals were added to the canvas, for showing the total profit, revenue, total oraders, unit sold, profit margin.

- Step 9 : The different types of charts were added to the report design area representing the sales insights with respect to region, products, unit sold. 

- Step 10 : The report was then published to Power BI Service.


# Snapshot of Dashboard (Power BI Service)

![Screenshot 2024-07-23 105739](https://github.com/user-attachments/assets/26ff756c-09bc-49ea-9927-920d0035e860)
![Screenshot 2024-07-23 120549](https://github.com/user-attachments/assets/6219cfde-e118-4300-ace4-59a2f7edd132)


# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### Total Number of Orders = 100
           
### TOTAL PROFIT
          SELECT 
            SUM([Total_Profit]) AS TOTAL_PROFIT
            FROM [dbo].[Amazon Sales data]
        
![image](https://github.com/user-attachments/assets/b97de748-b80a-4e8f-a7c9-13d01a3e392e)

  
  ### TOTAL REVENUE
             SELECT 
             SUM([Total_Revenue]) AS TOTAL_REVENUE
             FROM [dbo].[Amazon Sales data]
![image](https://github.com/user-attachments/assets/b560216a-322f-4d0d-930f-0977a5161158)


 ### TOTAL PROFIT in terms of region
              SELECT 
              Region, sum(total_profit) AS TOTAL_PROFIT 
              FROM [dbo].[Amazon Sales data]
              GROUP BY Region 
              ORDER BY Total_Profit DESC

![image](https://github.com/user-attachments/assets/651c050a-902d-4bfb-a91d-1a0eda9b526d)
![image](https://github.com/user-attachments/assets/8000ada4-9553-4488-9c46-ac4a3fedd5cf)

Sub-Saharan Africa is having more profit
 
 ### •	TOTAL_PROFIT in terms of item
           SELECT 
           top 5 Item_Type, sum(total_profit) AS TOTAL_PROFIT 
           FROM [dbo].[Amazon Sales data]
           GROUP BY Item_Type 
           ORDER BY Total_Profit DESC

![image](https://github.com/user-attachments/assets/6958017e-e4f6-4f23-adb4-1098b99f082f)
![image](https://github.com/user-attachments/assets/e09492ca-d0b0-4632-aca9-173c999a0134)


         
### Units sold in terms of item
         SELECT 
         top 5 Item_Type, sum(Units_Sold) AS UNITS_SOLD
         FROM [dbo].[Amazon Sales data]
         GROUP BY Item_Type 
         ORDER BY Units_Sold DESC
![image](https://github.com/user-attachments/assets/3368e338-04d9-4419-9d21-8a99baacde5f)
![image](https://github.com/user-attachments/assets/8e00729f-29d0-42cb-9c64-8fe53f57bc22)

### Units sold in terms of countries

         SELECT 
          top 5 Country, sum(Units_Sold) AS UNITS_SOLD
          FROM [dbo].[Amazon Sales data]
         GROUP BY Country 
         ORDER BY Units_Sold DESC
![image](https://github.com/user-attachments/assets/6ad635a2-4b70-4d16-aab9-b189eb722a61)
![image](https://github.com/user-attachments/assets/0ad66f91-eb02-41a5-8336-e7d74c1b7410)

•	The item_type office supplies are more sold is Australia
    SELECT 
       Country,sum(Units_Sold) as item
        FROM [dbo].[Amazon Sales data]
  
        WHERE Item_type = 'Office Supplies'
    GROUP BY Country
![image](https://github.com/user-attachments/assets/e8095040-4568-4135-ae41-34cfe1487500)
### Some other insights
•	The total sales is $137.35 million out of which total profit is $44.17 million.

•	The average profit margin and unit sold are $32.16 and $276.76 respectively.

•	“Cosmetics” products gave the highest sales.

•	The units sold more using offline channel.

•	Cosmetic products are very popular among people of Europe and  these products generated the highest profit ($14.56 million) of all items. So, it is advisable to create some marketing campaigns promoting Cosmetic products.

•	The year 2010 and 2017 has seen lowest number of orders.

•	The lowest rate of profit margin is in North American region and highest in Middle East and North Africa

•	The Sub-Saharan Africa region has seen the highest sales

•	“Cosmetics” products gave the highest profit and sales.

•	The year 2012 has seen the highest sales.

•	The office supply is more in Australia

•	The Country Sao Tome and Principe has highest sales.

•	The Sub-Saharan Africa region has seen the highest profit

•	The high priority items sold for offline channel.

•	The Meat product gave the least sales and profit.

•	There is no online sales channel for the Region of North America, indicating a higher focus on in-store distribution.

### Conclusion

Gain actionable insights to drive informed decision-making and optimize sales performance on Amazon. 
Identify growth opportunities, streamline operations, and enhance profitability with data-driven strategies








