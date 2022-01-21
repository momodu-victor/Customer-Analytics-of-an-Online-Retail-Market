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

## d. Data Loading:

Then, the pre-processed data is loaded and stored into the SQLite Database.

## e. Data Exploration:

From the data set we explore basic questions to have a better understanding of the data. For example, what are the most returned products? What are the countries with the lowest sales volume? How many times did a transaction occurred in a country? What are the sales of each country except UK? In some instances like the previous question, the UK is excluded as, the online retail market is based in the UK and it has the largest distribution, hence for proper deep dive analysis of other regions it has been excluded as it skews the data. Other questions like what are the quantity of products sold in all the countries except the UK? are also explored.

## f. Feature Engineering/Selection:

The following new feautures are included in the data set for better prediction:
- **Sales**: Price * Quantity
- **Recency**: How 'recently' has a customer made a purchase. The lower the value the better based on a 1-5 rank.
- **Frequency**: How often does a customer purchase. The higher the value the better, based on a 1-5 rank.
- **Monetary Value**: How much money does a customer spend. The higher the value the better, based on a 1-5 rank.
- **RFM Score**: It is a combination of the individual R, F, and M rankings to arrive to a RFM score.

## g. Segmentation and Clustering:

- At this point, we segment our customers using RFM and analyse customer behaviour.

- Every month active customer base can be passed into RFM + Kmeans Model to return the probability of churn for each customer (in business lingo, this is sometimes called a score of churn).

## h. Predictive Modelling:

- K-means is an unsupervised machine learning algorithm, which is used for data clustering. In k-means algorithm number of clusters K is predetermined and the algorithm iteratively assigns each data point to one of the K clusters based on the feature similarity.

- Implementation of K Means Clustering :

  - Preprocessing the Data
  - Determine the Number of Clusters
  - Running K Means Clustering on the Preprocessed Data
  - Analyse the clusters

## i. Data Visualization:

- The segments derived from the RFM Analysis and RFM is visualized on a Tree Map in the jupyter notebook.

- The unsupervised learning model, and choosen suitable number of clusters is visualized using a 3D plot in the jupyter notebook.

- Finally, the front-end of this project consists of a dynamic Power BI dashboard generated from the RFM and Kmeans segmentation and visualizes the results in a pleasing dashboard. This dashboard can be shared with sales managers in the different countries of the company.


# Data Retrieval
The data set for this project “Online Retail Data Set” is retrieved ina csv format from the “UCI Machine Learning Repository”. The UCI Machine Learning Repository is a collection of databases, domain theories, and data generators that are used by the machine learning community for the empirical analysis of machine learning algorithms. Since 1987, it has been widely used by students, educators, and researchers all over the world as a primary source of machine learning data sets. As an indication of the impact of the archive, it has been cited over 1000 times, making it one of the top 100 most cited "papers" in all of computer science.

This Online Retail data set contains all the transactions occurring for a UK-based and registered, non-store online retail between 01/12/2010 and 09/12/2011.The company mainly sells unique all-occasion gift-ware. Many customers of the company are wholesalers.

**Attribute Information**:

- **InvoiceNo**: The Invoice number is a 6-digit integral number uniquely assigned to each transaction. If this code starts with the letter 'c', it indicates a cancellation. It is a string data type.

- **StockCode**: This is the product (item) code. It is a 5-digit integral number uniquely assigned to each distinct product.

- **Description**: Product (item) name. It is a string data type.

- **Quantity**: The quantities of each product (item) per transaction. It is a numeric data type.

- **InvoiceDate**: The day and time when a transaction was generated. It is a datetime data type.

- **UnitPrice**: This is the product price per unit in Euros(€). It is a numeric data type. It is a string data type.

- **CustomerID**: This is a 5-digit integral number uniquely assigned to each customer.

- **Country**: Country name. Nominal. The name of the country where a customer resides.

**Source**: Dr Daqing Chen, Director: Public Analytics group. chend '@' lsbu.ac.uk, School of Engineering, London South Bank University, London SE1 0AA, UK.

**Link**: https://archive.ics.uci.edu/ml/datasets/online+retail

# Tools and Libraries used for the Project

- The Jupyter notebook environment (free), with Python 3.7 or higher will be used as the python integrated development environment (IDE) to compile all codes used for data preprocessing and data analysis steps.

- After performing some necessary pre-processing steps, the data is loaded and stored into an SQL database. For this project,we would be using the **SQLite** database which is a software library that provides a relational database management system.

- For the front end of this project, **Microsoft Power BI** Desktop application is used to build an interactive dashboard which can aid data-driven decision making for respective stakeholders and end users.

**Python packages used in project**

- numpy
- pandas
- matplotlib
- seaborn
- plotly
- math
- datetime
- squarify
- scipy
- sklearn

## Front End Visualization

A user interface dashboard is created with Microsoft Power BI which can be shared with country sales managers so they can be guided to the customers on the different segments and take specific actions on them.

- First, the data in the SQLite database is then connected to the visulazation tool(PowerBI) using an ODBC data connection and connect to a predefined “ODBC DNS”.

- Then a dashboard is created with Microsoft Power BI which can be shared with country sales managers so they can be guided to the customers on the different segments and take specific actions on them.

- This Microsoft Power BI dashboard can be shared with stakeholders in an enterprise environment as a web app.

- The dashboard file can be downloaded here:https://github.com/momodu-victor/Customer-Analytics-of-an-Online-Retail-Market-with-RFM-and-Kmeans-clustering/blob/9acf2fdd0c43519afe43ca310237420c81fa3c53/Customer%20Insight%20Dashboard%20(User%20Interface).pbix

- To view this dashboard,kindly download Microsoft PowerBI Desktop: https://powerbi.microsoft.com/en-us/downloads/

## Data Integration

In order to build a user interface for the cusomer segments, we would need to connect the datasource to the visualization tool. Hence, there is a need for **"Data Integration"**

By connecting dashboard directly to the datasource, the data and visuals on the dashboard would update real time as data is ingested into the SQLite database.

Here is the documentation of the process: https://github.com/momodu-victor/Customer-Analytics-of-an-Online-Retail-Market-with-RFM-and-Kmeans-clustering/blob/7ae8078308fb39e227c050ec1a18539b633ecb0a/User_Interface_Documentation.ipynb

