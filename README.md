# Udacity Starbucks Challenge

![Udacity Starbucks Capstone Project](https://user-images.githubusercontent.com/92649864/160221843-51d09d02-2267-4dba-b5bb-08536f6ad8e0.png)

## Project Overview & Motivation
Starbucks, one of the world’s most popular coffee shops, frequently provides offers to its customers through its rewards app to drive more sales. These offers can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free).

**Motivation:**The goal of this project is to find some factors and build a machine learning(ML) that predicts what makes a customer complete an offer(regardless of the offer type). I am mostly interested in the demographics as I believe that they are bigger factors than the offer types.

Firstly, to best analyze the data thoroughly, Exploratory Data Analysis(EDA) is performed to find the data representations & characteristics. In this step, I will get to know the data better, as well as clean it. Secondly, with the data provided, I will answer the above questions with the help of charts and various ML models which will be fed the data from a merged dataset which consists of the following: portfolio, profile, transactional.

## Datasets
For this project, the data sets are provided by Starbucks and Udacity in the form of three JSON files. These contains simulated data that mimics customer behavior on the Starbucks rewards mobile app.
-   portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
-   profile.json - demographic data for each customer
-   transcript.json - records for transactions, offers received, offers viewed, and offers completed
-   **[Starbucks_Capstone_notebook.ipynb](https://github.com/Mr-Chang95/Udacity-Starbucks-Challenge/blob/master/Starbucks_Capstone_notebook.ipynb)**: This is the Jupyter Notebook in which I performed all my work.

Here are the schema and explanation of each variable in the files:
~~~~~
**portfolio.json**
-   id (string) - offer id
-   offer_type (string) - type of offer ie BOGO, discount, informational
-   difficulty (int) - minimum required spend to complete an offer
-   reward (int) - reward given for completing an offer
-   duration (int) - time for offer to be open, in days
-   channels (list of strings)

**profile.json**

-   age (int) - age of the customer
-   became_member_on (int) - date when customer created an app account
-   gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
-   id (str) - customer id
-   income (float) - customer's income

**transcript.json**

-   event (str) - record description (ie transaction, offer received, offer viewed, etc.)
-   person (str) - customer id
-   time (int) - time in hours since start of test. The data begins at time t=0
-   value - (dict of strings) - either an offer id or transaction amount depending on the record
~~~~~
## Brief Description Of Findings
After having tried several different models, I found that the LGBM Classifier not only scored the highest f1-score with 0.58 which is the metric we have chosen to analyze the performance on test data, but also scored the highest accuracy. Therefore, I used this model to find the factors that can predict whether or not a customer will complete an offer. After fine tuning the model, I found that the top 3 most important features that impacts a customer completing an offer is the time taken to act on it, the customer's income and the year the customer became a member.

## Medium Article
For a more deatailed version of how I completed this project, please visit my [Medium article](https://medium.com/@mr.dcny/starbucks-capstone-project-udacity-16c65e59209c).

## Acknowledgements
I would like to thanks [Udacity](https://www.udacity.com/) and Starbucks(https://www.starbucks.com/) for providing me with the datasets to use for this project.
