# Week 1 Data Engineering Lab

## Scenario
A small online shop sends daily order data as a CSV file. A manager wants a reliable summary of valid orders by city.

## Pipeline plan
- Source: `orders.csv` (daily batch file)
- Raw destination: BigQuery table `de_intro.raw_orders`
- Curated output: query results after checking and filtering the data
- User of the output: shop manager

## Local data check
Before reporting, record at least two issues you found in the CSV and what you recommend doing with each.

1. Issue and recommendation: Duplicate row for order O-1006. Recommendation: Deduplicate records (using DISTINCT or GROUP BY on order_id) to avoid double-counting orders and revenue.
2. Issue and recommendation: Missing customer_city for order O-1004. Recommendation: Impute with 'Unknown' or filter out / flag for review so geographical aggregations remain accurate.

## What the pipeline does
Complete after the lab: In one sentence, describe how the data moves from the source to a useful output.

The pipeline extracts raw daily order data from a CSV file, loads it into a BigQuery staging table, and cleans/filters it using SQL to produce an accurate summary report of valid orders by city for the shop manager.