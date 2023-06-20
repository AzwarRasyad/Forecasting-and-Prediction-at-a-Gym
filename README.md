# Forecasting-and-Prediction-at-a-Gym

# Project Description

A fitness center franchise called Model Fitness is developing a customer engagement strategy based on analytical data.

One of the most common problems encountered by fitness center services and even other services is customer turnover or customer churn. How do you know that a customer has stopped using your service? You can indeed calculate the churn rate based on the number of people who delete accounts or don't renew their subscriptions. But sometimes, you can't know for sure if a client has actually quit: they may leave you without your knowledge.

Churn indicators can differ from one field to another. If a user purchases from an online store on an irregular but regular basis, you cannot say that the user has left your store. However, if for two weeks a user has not opened an online shop channel which is updated daily, then you can worry: your followers may have gotten bored and decided to leave you.

For fitness center businesses, a customer will be considered leaving if they do not return for one month. In fact, it is not necessarily true. A customer may not visit the fitness center for a month because he is on vacation, for example to Bali, and will return to visit the fitness center after the vacation is over. However, cases like this are rare. Usually, if a customer decides to join, then comes in a few times and then disappears, they are unlikely to come back.

To reduce the churn rate, Model Fitness has digitized some of its customer profiles. Your task is to analyze the profiles of these customers and develop customer retention strategies.

For that, you must:

- Learn how to predict the churn probability (for the next month) for each customer
- Create user segmentation by selecting the most dominant group, and describing the main characters
- Analyze the factors that most influence churn
- Draw basic conclusions and provide recommendations on how to improve customer service
  - Identify the target group
  - Recommend steps to reduce churn
  - Describe any other patterns you've encountered with regard to customer interactions

# Instruction

**Step 1. Download the Data**

Model Fitness provided you with CSV files containing data on churn for a given month and information on the month preceding it. The dataset includes the following fields:
- `'Churn'` — churn aktual untuk bulan terkait

Current dataset fields:
- User data for the preceding month
    - `'gender'`
    - `'Near_Location'` — whether the user lives or works in the neighborhood where the gym is located 
    - `'Partner'` — whether the user is an employee of a partner company (the gym has partner companies whose employees get discounts; in those cases the gym stores information on customers' employers)
    - `Promo_friends` — whether the user originally signed up through a "bring a friend" offer (they used a friend's promo code when paying for their first membership)
    - `'Phone'` — whether the user provided their phone number
    - `'Age'`
    - `'Lifetime'` — the time (in months) since the customer first came to the gym
    
Data from the log of visits and purchases and data on current membership status
- `'Contract_period'` — 1 month, 3 months, 6 months, or 1 year
- `'Month_to_end_contract'` — the months remaining until the contract expires
- `'Group_visits'` — whether the user takes part in group sessions
- `'Avg_class_frequency_total'` — average frequency of visits per week over the customer's lifetime
- `'Avg_class_frequency_current_month'` — average frequency of visits per week over the preceding month
- `'Avg_additional_charges_total'` — the total amount of money spent on other gym services: cafe, athletic goods, cosmetics, massages, etc.

File path: `/datasets/gym_churn_us.csv.` 

**Step 2. Carry out exploratory data analysis (EDA)**

- Look at the dataset: does it contain any missing features? Study the mean values and standard deviation (use the `describe()` method).
- Look at the mean feature values in two groups: for those who left (churn) and for those who stayed (use the `groupby()` method).
- Plot bar histograms and feature distributions for those who left (churn) and those who stayed.
- Build a correlation matrix and display it.

**Step 3. Build a model to predict user churn**

Build a binary classification model for customers where the target feature is the user's leaving next month.

- Divide the data into train and validation sets using the `train_test_split()` function.
- Train the model on the train set with the following two methods:
    - logistic regression
    - random forest
- Evaluate accuracy, precision and recall for both models using the validation set. Use to compare models. Which model gives the best results?

Don't forget to indicate the `random_state` parameter when you split the data and define the algorithm.

**Step 4. Create a User Cluster**

Select the column containing the churn data and define the cluster of objects (users):

- Standardize the data.
- Use the `linkage()` function to create a distance matrix based on a standardized feature matrix and graph the dendrogram. Note: dendrogram creation may take some time! Use the generated graph to estimate the number of clusters you can choose from.
- Train a clustering model with the K-means algorithm and predict its subscriber clusters. (Make the number of clusters `n=5`, so it will be easier to compare your results with those of other students. However, in real life, no one will give you such a hint. Therefore, going forward, you should make a decision based on the graph from the previous step.)
- Look at the average feature value for all the clusters. Does anything catch your eye?
- Make a feature distribution graph for each cluster. Did you notice anything?
- Calculate the churn rate for each cluster (use the `groupby()` method). Do the clusters differ in terms of churn rates? Which customer clusters are likely to leave, and which will remain loyal?

**Step 5. Formulate Simple Conclusions and Recommendations on Working with Customers**

Draw conclusions and formulate recommendations regarding customer interaction and retention strategies.
