
# Customer Segmentation and Product Recommendation Engine

## Dataset

This project uses the [Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Retail) from the UCI Machine Learning Repository.

- **Source**: [UCI Machine Learning Repository - Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Retail)
- **License**: Creative Commons Attribution 4.0 International (CC BY 4.0)
- **Attribution**: If you use this dataset in your own work, please cite the UCI Machine Learning Repository and the original data contributors.

> "Online Retail Dataset." UCI Machine Learning Repository, https://archive.ics.uci.edu/ml/datasets/Online+Retail.

## Installation
1. Clone this repository.
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt

## Table of Contents
1. [Introduction](#1-introduction)
2. [Why Customer Segmentation and Product Recommendation?](#2-why-customer-segmentation-and-product-recommendation)
3. [Workflow Overview](#3-workflow-overview)
4. Detailed Task Breakdown
   - [4.1. Find a customer transaction dataset](#41-find-a-customer-transaction-dataset)
   - [4.2. Engineer relevant features](#42-engineer-relevant-features-to-make-clusters-on)
   - [4.3. Implement Unsupervised Learning Techniques](#43-implement-unsupervised-learning-techniques)
   - [4.4. Create recommendation based system](#44-create-recommendation-system-based-on-clustering)

## 1. Introduction

This is my personal project on unsupervised learning prinicples and customer recommendation techniques.

## 2. Why Customer Segmentation and Product Recommendation?

Customer segmentation helps in identifying distinct groups within a customer base, allowing for targeted marketing and personalized experiences. Product recommendation engines enhance user experience by suggesting relevant products, increasing engagement and sales.

## 3. Workflow Overview

1. Find a customer transaction dataset
2. Apply feature engineering to produce relevant features.
3. Implement unsupervised learning techniques for customer segmentation:
   - K-means clustering using Scikit-learn
   - DBSCAN for density-based clustering
4. Make a recommendation system based on clustering

## 4. Detailed Task Breakdown

### 4.1. Find a customer transaction dataset

- I have used the following transaction dataset to apply my model on:
  - [Ecommerce Data](https://www.kaggle.com/datasets/carrie1/ecommerce-data/data)

### 4.2. Engineer relevant features to make clusters on.
- I engineered the following features for clustering the customers based on their purchasing behaviour:
   - Days Since Last Purchase
   - Total Transactions
   - Average Transaction
   - Days Since Last Purchase
   - Average Unit Per Transaction
   - Frequency of Transaction
   - No. of different products
   - Total Cancellations
   - Favorite Day of Week and Hour
   - Country

### 4.3. Implement Unsupervised Learning Techniques for Customer Segmentation

- **K-means Clustering**
  - Use Scikit-learn to implement K-means clustering.
  - Determine the optimal number of clusters using the elbow method or silhouette score.
 
  - The optimal number of clusters obtained for the above dataset were 3. The three clusters were as follows:
  - ### CLuster 0
       - These are minority customers of our store.
       - Infrequent customers evident from 'DaysSinceLastPurchase' and 'Frequency' means even when they did buy from the store they were irregular buyers
       - The total number of transactions are also less for each customer however whenever they did come their spend was high and also unit price was higher means           the products they purchased were expensive.
       - The domain of products they purchased was limited and werent open to new items. However their cancellation rate is lower meaning they trust our products            but are occasional high spenders and prefer particular range of products from our store.
       - They prefer to buy on weekdays specifically in the middle of week. They prefer afternoon hours for shopping.
       - The majority of them are from Germany.
   - ### CLuster 1
        - They are frequent buyers with high spend on each transaction and high unit price means they are regular buyers of high value items.
        - Also the domain of products purchased by them is quite varied. However their cancellation rate is quite high implying less satisfaction of products among           these people.
        - They buy on all days but prefer middle of week or weekends. Afternoon buyers.
        - These are all from UK.
        - As they are frequent big spenders it is important to work on cancellation rate for these customers.
   - ### Cluster 2
        - These are the majority customers of our store.
        - Their frequency varies from customer to customer and does not show any particular behaviour.
        - They are not high spenders and they do not have many transactions in our store. The average unit price of items is also less implying cheap products.
        - Their cancellation frequency is very low hence either they are satisfied by our products or the items are consummables which are cheap and cannot usually            be cancelled.
        - The items do not have wide variety.
        - They also prefer afternoons and are likely to buy on all days.
        - Mostly from UK.

    
- **DBSCAN**
  - Apply DBSCAN for density-based clustering.
  - Adjust parameters like epsilon and minimum samples to achieve meaningful clusters.
 
  - I was unable to implement this model on these dataset and there were no proper epsilon values for which any meaningful clusters could be made.

### 4.4. Create a recommendation system based on clustering
- Recommend out of the top 10 products in the cluster of a particular customer any 3 products which have not yet been bought by the customer. 


