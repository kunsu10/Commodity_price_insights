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

Business Question 2: What is the maximum difference between the prices of a commodity at one place vs the other 
for the month of Jun 2020? Which commodity was it for?

Algorithm:
Input: price_details: Id, Region_Id, Commodity_Id, Date and Retail_Price; commodities_info: Id and Commodity
Expected Output: Commodity | price difference;  Retain the info for highest difference
Step 1: Filter Jun 2020 in Date column of price_details
Step 2: Aggregation – MIN(retail_price), MAX(retail_price) group by commodity
Step 3: Compute the difference between the Max and Min retail price
Step 4: Sort in descending order of price difference; Retain the top most row

![image](https://github.com/user-attachments/assets/f122f190-e12e-488b-9710-a9da0e170e8e)

Business Question 3: Arrange the commodities in order based on the number of varieties in which they are available, 
with the highest one shown at the top. Which is the 3rd commodity in the list?

Algorithm:
Input: commodities_info: Commodity and Variety
Expected Output: Commodity | Variety count;  Sort in descending order of Variety count
Step 1: Aggregation – COUNT(DISTINCT variety), group by Commodity
Step 2: Sort the final table in descending order of Variety count

![image](https://github.com/user-attachments/assets/ac815dba-31e5-4f66-a479-0410dbcf7a2a)

Business Question 4: In the state with the least number of data points available. 
Which commodity has the highest number of data points available?

Algorithm:
Input: price_details: Id, region_id, commodity_id region_info: Id and State commodities_info: Id and Commodity
Expected Output: commodity;  Expecting only one value as output
Step 1: Join region info and price details using the Region_Id from price_details with Id from region_info
Step 2: From result of Step 1, perform aggregation – COUNT(Id), group by State; 
Step 3: Sort the result based on the record count computed in Step 2 in ascending order; 
		Filter for the top State
Step 4: Filter for the state identified from Step 3 from the price_details table
Step 5: Aggregation – COUNT(Id), group by commodity_id; Sort in descending order of count 
Step 6: Filter for top 1 value and join with commodities_info to get the commodity name

![image](https://github.com/user-attachments/assets/f3a2b004-b5c7-441c-90cf-3d8c0534002f)

Business Question 5: What is the price variation of commodities for each city from Jan 2019 to Dec 2020. 
			Which commodity has seen the highest price variation and in which city?
Algorithm:
Input: price_details: Id, region_id, commodity_id, date, retail_price 
	   region_info: Id and City 
	   commodities_info: Id and Commodity
Expected Output: Commodity | city | Start Price | End Price | Variation absolute | Variation Percentage;  
Sort in descending order of variation %

Step 1: Filter for Jan 2019 from Date column of the price_details table
Step 2: Filter for Dec 2020 from Date column of the price_details table
Step 3: Do an inner join between the results from Step 1 and Step 2 on region_id and commodity id
Step 4: Name the price from Step 1 result as Start Price and Step 2 result as End Price
Step 5: Calculate Variations in absolute and percentage; 
		Sort the final table in descending order of Variation Percentage
Step 6: Filter for 1st record and join with region_info, commodities_info to get city and commodity name

![image](https://github.com/user-attachments/assets/5fa33914-9279-4a2d-94c5-04d3bf4950bd)




