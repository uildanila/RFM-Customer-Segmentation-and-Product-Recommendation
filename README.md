# TheATeam JCDS Final Project - RFM Segmentation and Product Recommendation

This project is one of the processes of the Purwadhika Digital School Data Science Bootcamp program, and was compiled by the The A team consisting of :
* Bayu Fathurrahman
* Giovano Aditya Graha
* Nila Wildanul Husna

## **About**
In this project, we will use [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce?select=olist_products_dataset.csv) from Kaggle. This dataset contains details of more than 100.000 orders from 2016 to 2018, made at multiple marketplaces in Brazil. Its features allows us to analyze order from various dimensions: from order status, price, payment and freight price, to customer's location, product attributes, and reviews written by customers. We also geolocation data available.

For this project, we will apply RFM Analysis and K-means clustering to segment customers into different clusters based on their behavioral characteristics. And we will use recommendation system model to get product recommendation for the certain type of customer.

<br>

**Business Context**

It is very likely that you have come across the concept called ‘Know Your Audience’ once in a while. It is a crucial approach used by most businesses to identify different customer groups and their respective needs. The importance of the concept for a business is all about being capable of understanding and reaching customers better. This allows businesses to push their campaigns and products to customers in a more precise and personalised way.

*This concept gives businesses a chance to move from one-fits-all to more customer-centric strategies.* 

Customer Segmentation is a commonly used term for applying the ‘Know Your Audience’ concept to e-businesses. 

<br>

**Problem Statement**

Based on the dataset. We found that our customer base increase, so does our customer variety. Different customer have different needs, comes from different places, and have different interest, just to name a few. Pushing the same business approach or campaigns to all of our customers might not be efficient in terms of human resource, time, and cost. But in the reality, mostly customers only order once or twice and after that they didn't active anymore for a long time. Olist eCommerce need to have the capability to categorize the customers into several segmentation, so they can give the attention and offering promos, campaign, cashback, or recommendation to the right customers, so it might be more precise and personalized approach. Furthermore, if we could have the information based on the customer segmentation, we can maintain the customers and increase the loyal customers we have and we can even reduce the number of churn customers
after we know the characteristic of the certain customers, and create the right actions. So the business will still running and it might be increase the eCommerce's revenue.

<br>

**Analytic Approach**

Customer segmentation can be grouped into 3 types i.e. demographic segmentation, attitudinal segmentation, and behavioral segmentation. The idea is to segment customers based on when their last purchase was, how often they’ve purchased in the past, and how much they’ve spent overall. All three of these measures have proven to be effective predictors of a customer's willingness to engage in marketing messages and offers. In this scenario, since we have the customer's purchase history available with us it's easy to move forward with behavioral segmentation. In B2C business, RFM i.e. Recency-Frequency-Monetary are the most commonly used metrics to measure a customer's purchase behavior. Upon deriving the RFM metrics, the K-means algorithm is used to perform clustering.

<br>


**Goal**

In this project we'll try to separate customer into 4 segments using Recency, Frequency, and Monetary (RFM) analysis, and act on a particular group of customer (`Need Attention`) which has great recency score, but low frequency and monetary value. 

We'll be using recommendation system to recommend products to these customers that might be of interest to them, in order to increase frequency and monetary value, specifically from this group (`Need Attention`) of customer.

---

Segmentation Details:

- A : Loyal Customer
- B : Casual Customer
- C : Need Attention
- D : About To Sleep - Lost Customer


| Customer Segment | Segment Description |
| --- | ---|
| Loyal Customer | Do transaction recently, often and spend the most money. |
| Casual Customer | Bought most recently, but not often. In medium recency, frequency and monetary values. |
| Need Attention | Our *relatively* new customer, has the highest recency score but still low on the frequency and monetary value. |
| About To Sleep - Lost Customer | Lowest recency, frequency and monetary scores. This customer are lost and/ or has never made any transaction in a very long time. |
