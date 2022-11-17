# Amazon_Vine_Analysis
## Overview

The goal in this challenge was to analyze product reviews from Amazon, comparing those from users paid to review products through their Vine program, and those from unpaid users. The aim of the analysis was to determine whether any bias exists in the number of reviews that receive five stars depending on whether the reviewer was part of the paid Vine program or not. Due to considerations of time, computing power, and storage capacity, analyzing reviews across the vast array of products available from Amazon would be impractical. So, for the purposes of this challenge, only reviews of video game products on Amazon's U.S. website were considered. The set of reviews was pared down further to include only those reviews which received at least 20 votes, and where at least 50% of those votes indicated that the review was helpful. 

### Resources
- Data: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz
- Software: Amazon Web Services: Simple Storage Service (S3), Amazon Web Services: Relational Database Service (RDS), Google Colab, PySpark 3.3.1, pgAdmin4 v6.12, PostgreSQL v11.17

## Results

![DataFrame of paid reviews](https://github.com/tfish110/Amazon_Vine_Analysis/blob/main/Resources/paid_reviews_df.jpg)
![Summary stats of paid reviews](https://github.com/tfish110/Amazon_Vine_Analysis/blob/main/Resources/paid_reviews_summary.jpg)

- Above is a screenshot of the first 20 rows of the DataFrame for reviews that meet the criteria described above in the overview, restricted to only those reviews from paid members of the Vine program, followed by a screenshot of a summary of the statistics of interest
- In total, there were 94 reviews that met the analysis criteria from paid Vine reviewers
- Of those 94 reviews, 48 of them received five stars
- 51.06% of the reviews from paid Vine members received five stars 

![DataFrame of unpaid reviews](https://github.com/tfish110/Amazon_Vine_Analysis/blob/main/Resources/unpaid_reviews_df.jpg)
![Summary stats of unpaid reviews](https://github.com/tfish110/Amazon_Vine_Analysis/blob/main/Resources/unpaid_reviews_summary.jpg)

- Above is a screenshot of the first 20 rows of the DataFrame for reviews that meet the criteria described above in the overview, restricted to only those reviews from unpaid customers who were not members of the Vine program, followed by a screenshot of a summary of the statistics of interest
- In total, there were 40,471 reviews that met the analysis criteria from unpaid customers who were not Vine reviewers
- Of those 40,471 reviews, 15,663 of them received five stars
- 38.70% of the reviews from unpaid customers who were not Vine members received five stars 

## Summary

The evidence here would suggest that there may be some positivity bias for reviews generated from Vine program members. However, it is clear that these two groups have wildly different sample sizes, which makes it difficult to assess positivity bias without further statistical analysis. It's recommended that the an analysis of variance be conducted to compare the two different user groups; that way, despite the difference in sample size, it could be identified whether or not there is any statistical significance to the apparent disparity between the percentage of reviews that received five stars from each group.