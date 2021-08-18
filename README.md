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

There is no clear evidence of positivity bias among paid Amazon reviews. Although the mean rating for paid reviews is higher than the mean rating for unpaid reviews, this can be explained by the higher proportion of 1-star reviews among unpaid reviews.

## Method

### Data Storage

1. Created relational database using AWS RDS service.
2. Using pgAdmin and postgreSQL, created a server and connected it to the AWS database.
3. Created a database, along with table schemas, in pgAdmin.

<!-- AWS / pgAdmin Setup Screenshots -->
<kbd> <img src="https://github.com/amberteets/amazon-vine-analysis/blob/main/Resources/AWS_RDS.png" height="200"></img><kbd>

<div>
  <kbd>
    <img src="https://github.com/amberteets/amazon-vine-analysis/blob/main/Resources/pgadmin_server.png" height="250"></img>
    <img src="https://github.com/amberteets/amazon-vine-analysis/blob/main/Resources/pgadmin_server_conn.png" height="250"></img>
    <img src="https://github.com/amberteets/amazon-vine-analysis/blob/main/Resources/pgadmin_db.png" height="250"></img>
  </kbd>
 </div>

### ETL

1. Using PySpark in Google Colab Notebooks, extract AWS S3 dataset as a DataFrame.
2. Transform DataFrame with PySpark into three DataFrames matching the table schemas.
3. Export the data into the corresponding tables in pgAdmin.

### Analysis

1. Load review data from pgAdmin database and filter for reviews with an adequate number of helpful votes.
2. Calculate summary statistics for paid and unpaid reviews.
3. Plot rating trends for paid vs. unpaid reviews.

## Results

### Summary Stats

Of **38010** Amazon Pet Product reviews:
- **170** were paid and **37,840** were unpaid
- Mean / Median Review Rating
  - **Paid:** 3.93 Stars / 4.0 Stars
  - **Unpaid:** 3.76 Stars / 5.0 Stars
- Percent of 5-Star Reviews
  - **Paid:** 38.24%
  - **Unpaid:** 54.47%

<!-- Summary DataFrame -->
<div>
  <kbd>
    <img src="https://github.com/amberteets/amazon-vine-analysis/blob/main/Resources/review_summary.png" height=100></img>
  </kbd>
</div>

### Distribution

- The distribution of ratings among paid reviews is skewed to the right (towards 5 stars), indicating that paid reviews are generally more positive than negative.
- The distribution of ratings among unpaid reviews is bimodal, concentrated at 1-star and 5-star reviews.
- Unpaid reviews consist of more "extreme" ratings: 74% of unpaid reviews have either 1-star or 5-star ratings. Comparatively, only 42% of paid reviews are "extreme". 

<div>
  <kbd>
    <img src="https://github.com/amberteets/amazon-vine-analysis/blob/main/Resources/clustered_bar.png" width=460></img>
    <img src="https://github.com/amberteets/amazon-vine-analysis/blob/main/Resources/distribution.png" width=460></img>
  </kbd>
</div>

### Conclusion

There is no clear evidence of positivity bias among paid Amazon reviews. Although the mean rating for paid reviews is higher than the mean rating for unpaid reviews, this can be explained by the higher proportion of 1-star reviews among unpaid reviews. The data suggest that unpaid reviews follow the consumer-psychology hypothesis that buyers are more likely to leave a review if they are highly satisfied (5-star) or highly unsatisfied (1-star) with the product. In contrast, the paid reviews in this dataset reflect a more even distribution of ratings. This may be due to the fact that consumers were obligated to leave a review, and therefore the pool of reviewers was not as concentrated with people who had strong positive or negative feelings about the product.

### Limitations

- Proportion of paid reviews in dataset was very small (<1% of total reviews)

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
