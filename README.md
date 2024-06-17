# Sales Data Dashboard

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
