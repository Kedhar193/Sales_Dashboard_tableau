# Car Sales Dashboard

## Background
Our company operates as a car dealership selling various car models. To effectively monitor and analyze our sales performance, we are developing a dynamic and interactive Car Sales Dashboard using Power BI. This dashboard aims to visualize key performance indicators (KPIs) related to our car sales, providing insights to drive informed decisions and identify growth opportunities.

## Objectives
The objective of this project is to create a comprehensive Car Sales Dashboard in Power BI that visualizes critical KPIs and sales metrics. The dashboard will help us track:
- Year-to-Date (YTD) Total Sales
- Year-over-Year (YOY) Growth in Total Sales
- YTD Average Price and YOY Growth in Average Price
- YTD Cars Sold and YOY Growth in Cars Sold

## Problem Statement 1: KPI’s Requirement
The dashboard will provide real-time insights into our sales performance through various KPIs:
- YTD Total Sales
- YOY Growth in Total Sales
- YTD Average Price
- YOY Growth in Average Price
- YTD Cars Sold
- YOY Growth in Cars Sold

## Problem Statement 2: Charts Requirement
The dashboard will include the following visualizations to enhance data understanding and decision-making:
- **YTD Sales Weekly Trend**: A line chart illustrating the weekly trend of YTD sales.
- **YTD Total Sales by Body Style**: A Pie chart showing the distribution of YTD total sales across different car body styles.
- **YTD Total Sales by Color**: A Donut chart presenting the contribution of various car colors to YTD total sales.
- **YTD Cars Sold by Dealer Region**: A Bar chart showcasing YTD sales data based on different dealer regions.
- **Company-Wise Sales Trend in Grid Form**: A tabular grid displaying the sales trend for each company along with their YTD sales figures.


## Data Fields and Descriptions

This dataset contains information on car sales. Each field is described below:

1. **Car_id**: Unique identifier for each car sale.
2. **Date**: Date of the car sale.
3. **Customer Name**: Name of the customer.
4. **Gender**: Gender of the customer.
5. **Annual Income**: Annual income of the customer.
6. **Dealer_Name**: Name of the dealer or dealership.
7. **Company**: Manufacturer or brand of the car.
8. **Model**: Specific model of the car.
9. **Engine**: Type of engine in the car.
10. **Transmission**: Type of transmission in the car.
11. **Color**: Color of the car.
12. **Price ($)**: Sale price of the car.
13. **Dealer_No**: Unique identifier for the dealer.
14. **Body Style**: Body style of the car.
15. **Phone**: Phone number of the customer.
16. **Dealer_Region**: Geographical region of the dealer.

## Calculated Fields for Tableau Dashboard

These calculated fields are designed to be used within Tableau for further analysis:

### YTD Total Sales
SUM(IF YEAR([Date]) = YEAR(TODAY()) THEN [Price ($)] ELSE 0 END)


### YoY Sales Growth
(SUM(IF YEAR([Date]) = YEAR(TODAY()) THEN [Price ($)] ELSE 0 END) - SUM(IF YEAR([Date]) = YEAR(TODAY()) - 1 THEN [Price ($)] ELSE 0 END)) / SUM(IF YEAR([Date]) = YEAR(TODAY()) - 1 THEN [Price ($)] ELSE 0 END)


### PYTD Total Sales
SUM(IF YEAR([Date]) = YEAR(TODAY()) - 1 THEN [Price ($)] ELSE 0 END)


### YTD Cars Sold
SUM(IF YEAR([Date]) = YEAR(TODAY()) THEN 1 ELSE 0 END)


### PYTD Cars Sold
SUM(IF YEAR([Date]) = YEAR(TODAY()) - 1 THEN 1 ELSE 0 END)



### YoY Cars Sold Growth
(SUM(IF YEAR([Date]) = YEAR(TODAY()) THEN 1 ELSE 0 END) - SUM(IF YEAR([Date]) = YEAR(TODAY()) - 1 THEN 1 ELSE 0 END)) / SUM(IF YEAR([Date]) = YEAR(TODAY()) - 1 THEN 1 ELSE 0 END)



### YTD Avg Price
SUM(IF YEAR([Date]) = YEAR(TODAY()) THEN [Price ($)] ELSE 0 END) / SUM(IF YEAR([Date]) = YEAR(TODAY()) THEN 1 ELSE 0 END)



### YTD Avg Growth
(SUM(IF YEAR([Date]) = YEAR(TODAY()) THEN [Price ($)] ELSE 0 END) / 
SUM(IF YEAR([Date]) = YEAR(TODAY()) THEN 1 ELSE 0 END)) - 
(SUM(IF YEAR([Date]) = YEAR(TODAY()) - 1 THEN [Price ($)] ELSE 0 END) / 
SUM(IF YEAR([Date]) = YEAR(TODAY()) - 1 THEN 1 ELSE 0 END))

### Final Dashboard 

![Screenshot (82)](https://github.com/Kedhar193/Tableau-project/assets/115712936/1616334e-7723-45aa-9180-736179b633c1)

### Source

I completed this project following a youtube tutorial . This YouTube tutorial guided me through each step of the process, allowing me to achieve the desired results effectively.

link for source : https://youtu.be/KgJA9Up7O1s?si=v1xCbX5I4h4h92Kn
