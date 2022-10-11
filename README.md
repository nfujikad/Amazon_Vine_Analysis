# Amazon_Vine_Analysis

## Overview
The goal is to create a program utilizing Amazon's AWS to extract review data for products. Manufactureres can then use this program for a small fee and provide products to the program members in exchange for reviews.

The program focused on 1 of 50 datasets that contains reviews of a specific product. The chosen dataset contains 3,093,869 reviews on electronic products. 

### Purpose

The purpose is to determine if there is any bias toward favorable reviews (5-star reviews) from the members in the dataset.

Process:

-   ETL is done with ySpark to extract the dataset, transform the data, connect to an AWS RDS, and load the transformed data into pgAdmin. 
-	PySpark is used in Google Colab to determine if there is bias.
-	The last section includes a summary of the analysis.

## Results


**Data Filtering**

1.	Filter the data to retrieve all the rows where the review receives more than 20 votes.

2.	Filter the data again to retrieve all the rows where more than 50% votes are “helpful votes”.

3.	Filter the data to retrieve paid reviews by Vine and unpaid reviews.

**Paid Reviews**

<img width="589" alt="Screen Shot 2021-09-29 at 10 02 53 PM" src="https://github.com/nfujikad/Amazon_Vine_Analysis/blob/main/Resources/paid_reviews.png">

-	Among the filtered reviews for electronics, there are 1080 reviews marked as paid by Vine.
-	Among the 1080 Vine reviews, there are 454 favorable reviews (5-star reviews)
-	Overall, 42% paid reviews are 5-star reviews.

**Unpaid Reviews**

<img width="654" alt="Screen Shot 2021-09-29 at 10 03 14 PM" src="https://github.com/nfujikad/Amazon_Vine_Analysis/blob/main/Resources/unpaid_reviews.png">

-	Among the filtered reviews for electronics, there are 49673 reviews marked as unpaid.
-	Among the 49673 unpaid reviews, there are 23043 favorable reviews (5-star reviews)
-	Overall, 46% unpaid reviews are 5-star reviews.

## Summary

- Looking over the dataset, 42% paid customers provided 5-star reviews, 4% less compared to the 46% unpaid users who provide 5-star reviews. Therefore, it is inconclusive whether there is a positivity bias towards favorable reviews contributed by paid users. 
- It is also insufficient to determine whether there is any bias based on one set of analysis. As recommendations, the following analysis could further investigate:
  1. The percentage of 1- and 2-star reviews (low reviews) of paid and unpaid reviews. To determine wether paid customers tend to avoid leaving low reviews.
  2. The statistical distribution of the reviews: mean, median, mode of paid and unpaid reviews, to analysis the review distributions by each type of customer.



