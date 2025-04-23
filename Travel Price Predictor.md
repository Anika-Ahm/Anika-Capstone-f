# Travel Price Predictor: Find you next travel destination
**Estimating Flight Costs Using Historical City-Pair Airfare Data**

## Project Overview
## Problem Area
Flight prices are notoriously inconsistent—fluctuating due to demand, time of booking, seasonality, and destination popularity. These variations create challenges for budget-conscious travelers.


This project aims to build a predictive model that estimates the cost of air travel between U.S. cities based on historical airfare trends and trip characteristics. The ultimate goal is to help consumers make more informed booking decisions and help travel services optimize pricing strategi


## Stakeholders

- Travelers planning budget-friendly trips
- Airlines optimizing fare strategies
- Travel agencies and booking platforms
- Developers building travel planning tools

## Data Science Approach

We use **Linear Regression** to model airfare as a function of:

- Travel quarter (seasonality)
- City-pair popularity (passenger volume)
- Price 

Linear regression is chosen for its interpretability and effectiveness with continuous target variables like price.

## Datasets

**1. Consumer Airfare Report: Table 3 - City-Pair Markets With A Substantial increase In Average Fare**  
[https://data.transportation.gov/Aviation/Consumer-Airfare-Report-Table-3-City-Pair-Markets-/hc34-r2dt/about_data]


**2.Consumer Airfare Report: Table 4 - City-Pair Markets With A Substantial Decrease In Average Fare**  
[https://data.transportation.gov/Aviation/Consumer-Airfare-Report-Table-4-City-Pair-Markets-/bpm3-b8r4/about_data]


### Data Dictionary 

| Column Name | Description | Data Type |
|------------|-------------|------------|
| Year | Year of observation | Integer |
| Quarter | Quarter of the year (1-4) | Integer |
| City Pair | Origin and destination cities | String |
| citymarketid_1 |City market ID is an identification number assigned by US DOT to identify a city market. Use this field to consolidate airports serving the same city market | Integer |
| citymarketid_2 |City market ID is an identification number assigned by US DOT to identify a city market. Use this field to consolidate airports serving the same city market | Integer |
| city1 | City1 is used to consolidate airports serving the same city market |String|
| city2 | City2 is used to consolidate airports serving the same city market |String |
| cur_passengers | Current year passengers | Float |
| cur_fare | Current year fare | Float |
| ly_fare | Last year fare | Float |
| ly_passengers | Last year passengers | Float |
| amount_change | Fare amount difference between current year and previous year | Float |
| percent_change | Fare percentage difference between current and previous year| Float |
| amount_change_pax | Passenger number difference between current year and previous year | Float |
| percent_change_pax | Passenger percentage difference between current and previous year | Float |

## Methodology

- **Data Cleaning** – Removing duplicates, droping unecessary colunms to simplify data. filtering for consistent city pairs
- **Categorize** the models by fare price, city, and volumn of passesngers
- **Modeling** – Fitting a linear regression model to predict average fare nxt year and logistic model to make desicions easier. 
- **Visualization** – Displaying pricing trends over time and model accuracy

## Expected Benefits

- Help users understand when and where to book for the best airfare
- Give travel companies insights into demand and pricing trends
- Reduce uncertainty in travel budget planning
- Help undecided Travelars

## Limitations

- Best data for such models are Airline APIs, where thay have largers and more recent databases for more accurate model.  
- U.S. domestic data only
- External shocks like pandemics, recssesions are not modeled

## Future Plans

- Scrape real-time pricing data for validation
- Extend analysis to international flights
- Add interactive dashboards for user exploration
- Combine with hotel pricing models for full trip cost prediction