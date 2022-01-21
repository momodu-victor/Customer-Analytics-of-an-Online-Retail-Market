# Understanding consumer behavior using RFM analysis and K-Means clustering: What is the likelihood of a customer leaving the online retail market?

# Motivation
The Business-to-Consumer (B2C) Online Retail realm is by nature a competitive environment that is currently facing high levels of investment to attract new customers while focusing on customer loyalty and profitability to increase market share. 

Hence it is crucial for companies to understand what the underlying causes behind a customer leaving the business. 
Therefore, firms are increasingly providing more focus to strategies in which they can reduce their customer churn rate while identifying customers' that bring true value. 
According to Renjith (2015), churn rate is the ratio of customers who part away with the firm in a specific time period. 

One of the best mechanisms to retain current customers is to identify any potential churn and respond fast to prevent it.
Detecting early signs of a potential churn, recognizing what the customer is looking for by the movement and automating personalized win back campaigns are essential to sustain business in this era of competition (Neslin et al., 2006). 

The following project aims to explore the likelihood of a customer leaving the online retail market through RFM (Recency, Frequency, and Monetary) analysis. 
RFM is  a  proven  marketing  model  for  behaviour  based customer segmentation. It groups customers based on their transaction history – how recently, how often and how much did they transacted.

Each customer is assigned a score to predict customers that are at risk to churning while exploring different question from 
- Who are the best customers? 
- Which of your customers can be retained? 
- Who are the loyal customers? 
- Where are our new customers?

This project explores which customers are truly at risk to churn and it provides insights on which target incentives would be useful for customers to stay and extend the customer’s lifetime value (CLV) in the online retail market.

# Project Plan: Identify the tasks to be done to answer the question

## a. Business Understanding:

Retaining customers is one of the most critical challenges in the online retail market. Hence, using customer transaction data to investigate the likelihood of a customer leaving the online retail market to understand their customer churn is crucial to extend their customer’s lifetime value (CLV) and identify loyal customers.

## b. Data Mining:

The data set for this project “Online Retail Data Set” is retrieved in a csv format from the “UCI Machine Learning Repository”. The UCI Machine Learning Repository is a collection of databases, domain theories, and data generators that are used by the machine learning community for the empirical analysis of machine learning algorithms. Since 1987, it has been widely used by students, educators, and researchers all over the world as a primary source of machine learning data sets. As an indication of the impact of the archive, it has been cited over 1000 times, making it one of the top 100 most cited "papers" in all of computer science.

## c. Data Cleaning:

As a next step, this project will evaluate the missing values within the data set to better understand how to deal with them. First, we search for patterns within the variables through visual inspection. There, we speculate how the distribution of the missing values would look like if they were available by discussing if the missing data is “missing completely at random”, “missing at random” or “not missing at random.” Also data types are checked, to ensure that accuracy in the analysis. Before doing the analysis and prediction, the data is checked if it is normalized. Furthermore, it is ensured that all column names are well described. Some of the country names that are not understandable such as 'ERIE' into 'Ireland'. Dropped rows that contained Missing Customer ID,Missing Stock Description, Abnormal Stock Codes that did not conform to the expected format, such as Stock Codes that started with letters, and had less than 5 digits. These tended to be from manual entries (Stock Code ‘M’), postage costs (Stock Code ‘DOT’) and cancelled orders (Stock Codes starting with ‘C’). However, I retained Stock Codes that ended with letters, as these tended to indicate product variations (e.g. pattern, color).

## d. Data Exploration:

From the data set we explore basic questions to have a better understanding of the data. For example, what are the most returned products? What are the countries with the lowest sales volume? How many times did a transaction occurred in a country? What are the sales of each country except UK? In some instances like the previous question, the UK is excluded as, the online retail market is based in the UK and it has the largest distribution, hence for proper deep dive analysis of other regions it has been excluded as it skews the data. Other questions like what are the quantity of products sold in all the countries except the UK? are also explored.

## e. Feature Engineering/Selection:

The following new feautures are included in the data set for better prediction:
- **Sales**: Price * Quantity
- **Recency**: How 'recently' has a customer made a purchase. The lower the value the better based on a 1-5 rank.
- **Frequency**: How often does a customer purchase. The higher the value the better, based on a 1-5 rank.
- **Monetary Value**: How much money does a customer spend. The higher the value the better, based on a 1-5 rank.
- **RFM Score**: It is a combination of the individual R, F, and M rankings to arrive to a RFM score.

## f. Segmentation and Clustering:

At this point, we segment our customers using RFM and analyse customer behaviour.

We further apply the unsupervised k-means clustering algorithm on these parameters to group similar customers. Note the input values to this algorithm have to be continuous variables.K-means is a popular approach for clustering because of simplicity of implementation and been widely used in market segmentation. The number of suitable clusters would be determined by using the elbow method.

Every month active customer base can be passed into RFM + Kmeans Model to return the probability of churn for each customer (in business lingo, this is sometimes called a score of churn).

## g. Data Visualization:

The segments derived from the RFM Analysis is visualized in a Tree Map.

The unsupervised learning model, and choosen suitable number of clusters is visualized using a 3D plot.
