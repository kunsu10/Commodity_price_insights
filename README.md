# Commodity Price Intelligence: A SQL-Driven Analysis of Market Trends (2019-2020)
**Business Objective:**

In an ever-changing retail landscape, analyzing commodity pricing trends is crucial for stakeholders including retailers, consumers, and policy makers. This project performs a comprehensive analysis of commodity prices across different regions and time periods to extract actionable insights.

The objective of this project is to:

- Identify the top costliest commodities over time and compare them across years.
  
- Highlight regional price disparities and the most volatile commodities.

- Analyze variety richness of commodities to understand market diversity.

- Explore geographic data coverage and identify data gaps.

Quantify price variation over time and geography to support decision-making in pricing strategy, supply chain planning, and consumer awareness.

Using structured SQL queries and window functions, this project delivers high-value insights derived from multi-dimensional datasets, simulating real-world business intelligence scenarios in retail analytics.

**Queries**

Business Question 1: Get the common commodities between the Top 10 costliest commodities of 2019 and 2020.

![image](https://github.com/user-attachments/assets/98e0e066-839e-4232-9f51-84296a020cef)

Answer: 
Common Commodities in Top 10 (2019 & 2020): Shoes-Gents Coffee Black Pepper Soft Cake Meat Saree Ghee

The above list represents the commodities that appeared in the Top 10 costliest commodities for both years — 2019 and 2020. The result was obtained by querying and comparing the top commodities based on their average prices for each year and selecting the common entries.

Business Question 2: What is the maximum difference between the prices of a commodity at one place vs the other 
for the month of Jun 2020? Which commodity was it for?

![image](https://github.com/user-attachments/assets/f122f190-e12e-488b-9710-a9da0e170e8e)

Answer:
In June 2020, Coffee had the maximum price variation across different regions, with a price difference of ₹2435.00.

Business Question 3: Arrange the commodities in order based on the number of varieties in which they are available, 
with the highest one shown at the top. Which is the 3rd commodity in the list?

![image](https://github.com/user-attachments/assets/f83de242-b87c-4412-9f25-e172499cae14)

Answer: 
Coffee is the 3rd commodity in the list based on the number of varieties.

Business Question 4: In the state with the least number of data points available. 
Which commodity has the highest number of data points available?

![image](https://github.com/user-attachments/assets/f3a2b004-b5c7-441c-90cf-3d8c0534002f)

Answer:
The state with the least number of data points is Arunachal Pradesh. Within this state, the commodity with the highest number of data points is Rice, with a count of 9.

Business Question 5: What is the price variation of commodities for each city from Jan 2019 to Dec 2020.

![image](https://github.com/user-attachments/assets/5fa33914-9279-4a2d-94c5-04d3bf4950bd)

Answer:
Between Jan 2019 and Dec 2020, Coffee in Malda showed the highest absolute price variation, increasing by ₹1630.00.




