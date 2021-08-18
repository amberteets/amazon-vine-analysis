# Amazon Vine Analysis

## Overview

Using Big Data to investigate the presence of positivity bias among paid Amazon reviews versus unpaid reviews in the Pet Products category.

### Background

The Amazon Vine program is a service that allows manufacturers and publishers to increase the number of reviews for their products. Companies pay Amazon a fee and furnish free products to customers, who are required to publish a review.

This analysis seeks to understand if there is bias towards favorable reviews from paid Vine program participants.

### Objectives

- Use PySpark to process data
- Use AWS S3 and relational databases for cloud storage
- Use Pandas and Plotly to complete analysis of Amazon customer reviews

### Summary of Results

<!-- 1-2 sentences summarizing findings -->

## Method

### Data Storage

1. Created relational database using AWS RDS service.
2. Using pgAdmin and postgreSQL, created a server and connected it to the AWS database.
3. Created a database, along with table schemas, in pgAdmin.

### ETL

1. Using PySpark in Google Colab Notebooks, extract AWS S3 dataset as a DataFrame.
2. Transform DataFrame with PySpark into three DataFrames matching the table schemas.
3. Export the data into the corresponding tables in pgAdmin.

### Analysis

1. Load review data from pgAdmin database and filter for reviews with an adequate number of helpful votes.
2. Calculate summary statistics for paid and unpaid reviews.
3. Plot rating trends for paid vs. unpaid reviews.

<!--
## Results


Analysis of 38010 Amazon reviews for pet products yielded the following results:

<kbd> <img src="https://github.com/amberteets/amazon-vine-analysis/blob/main/Resources/review_summary.png" /> <kbd>

-->

## Resources

### Languages
  
- Python
- SQL

### Tools

- Google Colab
- Jupyter Notebook
- PySpark
- Pandas
- Plotly
- Matplotlib
- pgAdmin
- Amazon Web Services (S3, RDS)
