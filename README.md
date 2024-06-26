# Coffee Beans Sales Analysis Project
![](https://github.com/temee0/Coffee-Beans-Sales-Analysis-Project/blob/main/intro%20pic.jpg)

## Introduction
This project involves analyzing sales data for a fictional coffee bean store. Our goal is to uncover insights that answer key questions and guide data-driven decisions.  
Using descriptive, diagnostic, and prescriptive analysis approach, we summarize sales metrics, diagnose trends, and provide actionable recommendations. This approach helps us understand past performance and make informed choices for future success.   
**_Disclaimer_** :  _The dataset used in this analysis is sourced from Kaggle and is entirely fictitious. Therefore, this report does not represent any specific company, institution, or country. Rather, it serves as a demonstration of data analysis and visualization skills._

## Problem Statement
#### 1. Popular Picks:
What are the top 2 coffee types that customers are loving the most?
#### 2. Order Averages:
On average, how much coffee are our customers ordering?
#### 3. Global Snapshot:
How are our customers spread out across the US, UK, and Ireland?
#### 4. Loyalty Rewards:
How many customers should be part of our loyalty program?
#### 5. Engagement Challenge:
How many customers haven't placed an order yet, and what strategies can we use to encourage them?
#### 6. Discount Eligibility:
Who qualifies for our 10% discount promotion?

## Analysis Toolkits
### 1. Microsoft Excel:
- Data cleaning
- Formulas and functions
### 2. Structured Query Langauge (MySQL):
- Database creation
- Analysis
### 3. Microsoft PowerBI:
- Visual tools
- DAX
- Modelling
- Page navigation
- Buttons
- Bookmarking
- Filters
- Tooltips

## Modelling
Automatically derived relationships have been adjusted to remove or replace unwanted relationships with the required relationships.

![](https://github.com/temee0/Coffee-Beans-Sales-Analysis-Project/blob/main/Coffee%20data%20model.jpg)

## Visualization
This report comprises of 2 pages 
- Sales page
- Customer page
      
You can interact with the report [here](https://drive.google.com/file/d/1N5sDq5QJzycIE82mu3o_LXcJKqAS8d5W/view?usp=drivesdk)

## Sales
![](https://github.com/temee0/Coffee-Beans-Sales-Analysis-Project/blob/main/sales%20page.jpg)
- Total revenue generated between january 2019 to september 2022 is $43,381.
- Total profit generated between january 2019 to september 2022 is $4,340.
- There was a significant revenue increase between 2020 to 2021, where 2021 revenue increased by 11.97%.
- The United states accounts for 80% of the total revenue.
- The Liberica and Excelsa coffee types generates the most profit.

## Customers
![](https://github.com/temee0/Coffee-Beans-Sales-Analysis-Project/blob/main/customer%20page%200.jpg)
- The total number of customers between january 2019 to september 2022 is 1000.
- The total number of customers that should be issued a loyalty card is 487.
- Average quantity of coffee beans bought by customers is 3.56.
- The top two most ordered coffee beans by customer are Arabica and Excelsa and they both account for 51% of the total orders.
- The countries with the highest and lowest numbers of customers are the United states and United kingdom respectively.
- The total number of customers that should be eligible for a 10% discount are 293.
- The total number of customers that are yet to place an order are 87.

## Conclusion
The business has generated a total revenue of $43,381 and a profit of $4,340 from January 2019 to September 2022.

The United States is the dominant market, contributing 80% of the total revenue. This suggests a strong foothold in the US market and potential opportunities for further expansion.

Liberica and Excelsa coffee beans generate the most profit indicating higher profit margins compared to other coffee beans. 

The presence of 87 customers who are yet to place an order signals a potential area for improvement in customer engagement or outreach. 

## Recommendations
While the US market is lucrative, it's also important for the business to diversify its geographical reach to mitigate risks associated with relying too heavily on one market. It is important to explore opportunities in other regions or countries to help spread risk and unlock new revenue streams. This could involve opening new stores in strategic locations, expanding distribution channels, or increasing marketing efforts to reach more customers in other countries or regions.

Since Arabica and Excelsa coffee beans are the top-selling varieties, the business should ensure ample availability of Arabica and Excelsa coffee beans to meet customer demand. Additionally, it could consider promoting these varieties more prominently to further capitalize on their popularity.

I created a metric that determines customers that get added to the loyalty program after they have exceed a certain amount of purchase value. A total number of 487 customers qualified for a loyalty card, starting a loaylty program is  a strategic move to enhance customer retention and encourage repeat business. Loyalty programs often incentivize customers to choose your business over competitors.  
With a total of 487 customers eligible for a loyalty card, you have the opportunity to build stronger relationships with these individuals and potentially increase their lifetime value to your business. 
Implementing a well-designed loyalty program can not only drive customer loyalty but also contribute to increased revenue and profitability over time. It's important to communicate the benefits of the program effectively to customers and ensure that the rewards offered are compelling enough to encourage participation.

I created another metric that i used to identify 293 customers who qualify for a 10% discount. This presents an opportunity to incentivize repeat purchases and foster customer loyalty. 
Offering discounts can encourage these customers to make more frequent purchases and potentially increase their overall spending with the business.

It is important to incentivize the first purchase of the customers that are yet to place an order by offering special incentives or discounts to encourage these customers to make their first purchase. Reach out to these customers to gather feedback on their reasons for not making a purchase. Understanding their concerns or barriers can provide valuable insights into areas where the business can improve its offerings or customer experience to attract and convert them into active customers.

## Data Transformation/cleaning
Data was efficiently cleaned and transformed using Microsoft Excel functions, Power BI, and the DAX language, as well as SQL. Some of the applied steps are listed below:
- Using the Excel filter functionality and replace tools to find errors and make corrections in Excel.
- Deleting duplicate rows. 
- Adding a sales field to the Orders table by calculating how much was earned on each order, multiplying unit price by quantity. <kbd style="background-color: #B8AFAF; padding: 10px; border-radius: 5px;">
  =Quantity * Unit price</kbd>
- I created metrics to determine which customers should be eligible for a loyalty card, following these steps:  
  1. I calculated the average sales per customer <kbd style="background-color: #f2f2f2; padding: 10px; border-radius: 5px;">
=AVERAGE(M2:M958)</kbd>   
  2. I added the sales field from the order table to the customer table using the VLOOKUP function. <kbd style="background-color: #f2f2f2; padding: 10px; border-radius: 5px;">
=VLOOKUP(A2,orders!$C$1:$M$958,11,FALSE)</kbd>  
  3. I added a loyalty customer field by selecting customers with sales values above the average sales value as eligible for the loyalty program. <kbd style="background-color: #f2f2f2; padding: 10px; border-radius: 5px;">
=IF(J2>45,"yes","no")</kbd>  
  4. I calculated the total number of customers eligible for a loyalty card using the DAX CALCULATE function.  <kbd style="background-color: #f2f2f2; padding: 10px; border-radius: 5px;">
Loyalty Customers = CALCULATE([Total Customers],customers[Loyalty_card] = "yes")</kbd>   
- I created a metric to determine customers that qualify for the 10% discount promo using the DAX CALCULATE function.  <kbd style="background-color: #f2f2f2; padding: 10px; border-radius: 5px;">
10% off discount = IF([Total Revenue]>50,"Yes","No")  
customers eligible for discount = CALCULATE(COUNTROWS(orders), orders[10% off discount] = "yes")</kbd>   
- I determined the total number of customers who are yet to place an order using an SQL query. <kbd style="background-color: #f2f2f2; padding: 10px; border-radius: 5px;">
select count(c.customer_id) from customers as c   
  left join orders as o  
  on c.customer_id=o.customer_id  
  where o.order_id is null
</kbd>

---

![](https://github.com/temee0/Coffee-Beans-Sales-Analysis-Project/blob/main/coffee%20conclusion%20pic.jpg)  
#### Thank you for taking the time to read through this report.


