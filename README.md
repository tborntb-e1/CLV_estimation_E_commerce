### Summary
This project compares CLV estimation using statistical model (BTYD) and Machine Learning Model (random forest regressor and XGBoost). BTYD performs better in terms of RME and worse than the other two, indicating that predictions from BTYD model have less extreme values. The statistical model requires only customer’s recency, frequency, monetary value, and age of the customers as inputs to estimate CLV of a defined k-period.  

- `customer_id` represents a unique identifier for each customer.
- `frequency` represents the number of *repeat* purchases that a customer has made, i.e. one less than the total number of purchases.
- `T` represents a customer’s “age”, i.e. the duration between a customer’s first purchase and the end of the period of study. In this example notebook, the units of time are in weeks.
- `recency` represents the time period when a customer made their most recent purchase. This is equal to the duration between a customer’s first and last purchase. If a customer has made only 1 purchase, their recency is 0.
- `monetary_value` represents the average value of a given customer’s repeat purchases. Customers who have only made a single purchase have monetary values of zero. 


The machine learning model, on the other hand, require a label, the actual customer spend in the next k-period in the training set. ML model in this project is employed to benchmark BTYD model performance. Another interesting way of using ML model in CLV is through a two-stage learning: 1) classify users based on their likelihood of making a purchase in k period. 2) Estiamte the value of purchases of customers who is predicted to make a purchase. Due to the limitation of the dataset, this project will not consider this method.


After obtaining customers' CLV, I used K-means for customer clustering task. 


**The project answers the following business questions:**
1. Which customers have the highest spend probability in next 6 months? This is used to inform targeted campaign such as sending out email notification. 

2. Which customers were predicted to purchase but didn't? (missed opportunities) Why? 

3. How should the marketing team allocates budget to improve sales?





**These turns into analytical questions:**
* Predict how much a customer will spend in next k period, including the likelihood of 'alive' and the probability of purchasing given 'alive'.
* What is the purchase amount a customer make. 
