# RFM Customer Segmentation and Product Recommendation

<img width="1431" alt="Screenshot 2022-07-05 at 22 39 14" src="https://user-images.githubusercontent.com/73053128/177365589-3ac0a5ff-e994-443a-b4a9-1f1440ef5504.png">


This project is one of the processes of the Purwadhika Digital School Data Science Bootcamp program, and was compiled by the The A team consisting of :
* Bayu Fathurrahman
* Giovano Aditya Graha
* Nila Wildanul Husna

Deployment of model can be accessed on [ateamfinalproject.herokuapp.com](https://ateamfinalproject.herokuapp.com/)

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

![Customers Growth](https://user-images.githubusercontent.com/73053128/177360828-d0666ea0-5ae0-44fb-9dc5-7028eb9418d8.png)

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

---

**RFM Customer Segmentation Result**

<img width="1303" alt="Screenshot 2022-07-05 at 22 34 14" src="https://user-images.githubusercontent.com/73053128/177364679-12d82410-9c3f-4baf-a770-d64d8243beac.png">


---

**Recommendation System**
<br>
<img width="365" alt="Screenshot 2022-07-05 at 22 23 44" src="https://user-images.githubusercontent.com/73053128/177362786-c69b4271-fe83-407b-84e6-caca42664b9a.png">

Based on the result, recommendation system with SVD using cross validation giving the lowest MAE's value in test. So, used this model for our recommendation system that we wanted to build and tuning the model to get the best recommendation system result.

**Product Recommendation based on SVD Model**
<img width="850" alt="Screenshot 2022-07-05 at 22 25 46" src="https://user-images.githubusercontent.com/73053128/177363362-258ed93b-ed2e-4e1b-ac94-0310c6ec3e86.png">

We could see from the top 3 product recommendation above, we can offering the product that have a relationshipt with the previous product purchased by customers. This might be increase the requency and monetary customers in Segment 'C', because we can give the recommendation personalized to each customers. Basically, this product recommendation model can be also implemented to the other customer's segment. For this project, we can assumed that we can giving different recommendation treatment for other customers segment.  


**Conclusions**
- As seen from customer growth, number of order, and total sales overtime graphs from our EDA, which shows the same trend over the span of 2 years, we could infer that the majority of transactions happened are from new customers. Meaning that our customerbase is still rapidly growing, and we should give our attention to these types of customers as well, to increase their frequency and monetary value.

- Around 42% of our customers are based in Sao Paulo, and we also know that `delivery time` affects `review score`, in other words, it affects customer satisfaction and overall shopping experience. Therefore, we could consider building warehouse(s) in Sao Paulo in order to cut `delivery time` and maybe even `freight value`.

- Using our RecSys model, customer will get product recommendation based on their purchase history, products that are recommended to the customer are the products that is related to the product previously bought by the customer and has a high review score given by other customers.

- With our RecSys model, we got MAE score of *0.98, meaning that predicted `review score` could be off by around *+0.98** or *-0.98* compared to the actual `review score`. However, as our focus is not to predict customer's review but to *recommend* products that customer might be interested in, these result doesn't necessarily mean that the products we recommended would miss.

- We've done customer segmentation in order to categorize customer's characteristics, and discover that customer class `C` have potential to be our loyal customer if we increase their frequency and monetary value. Therefore, in this project, we decided to focus on this group of customer.

- As seen from customer growth, number of order, and total sales overtime graphs from our EDA, which shows the same trend over the span of 2 years, we could infer that the majority of transactions happened are from new customers. Meaning that our customerbase is still rapidly growing, and we should give our attention to these types of customers as well, to increase their frequency and monetary value.

**Recommendations For Business**

Based on our analysis and modeling, there are several things we could try to increase our customer engagement based on customer's segmentation such as:
- For class `C` which is our target user, we could recommend them product recommendations from RecSys model that we've built based on their purchase history. Since customer class `C` have a good recency score, it is likely that they will visit our platform again in the future, therefore we could put this personalized recommendation on their homepage on our website or app.

- For class `A` and `B`, we could implement loyalty program such as **give away cashback promotion**, which hopefully will interest customers in this segments and encourage them to keep making transactions.

- For class `D`, we could try to email blast them with our product recommendation and/or other promotions such as `Comeback Customer Sale` or we can learn the characteristic of this customer segment to prevent or reduce the number of the Lost Customers in the future.

- Most of our customers (around 42%) are based in Sao Paulo, and we also know that `delivery time` affects `review score`, in other words, it affects customer satisfaction and overall shopping experience. Therefore, we could consider building warehouse(s) in Sao Paulo in order to cut `delivery time` and maybe even `freight value`.

**Recommendations For Project's Development**
- Try and develop current model to get a better result, using different algorithm such as SlopeOne, CoClusterin, SVDpp, etc.

- Tuning using different hyperparameter values, to get a better metrics (MAE).

- Use different approach other than RFM, such as Customer Lifetime Value, Customer Churn etc.

