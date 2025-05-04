# Customer_Segmentation
This project aims to perform customer segmentation on a Mall customer dataset using the K-Means clustering algorithm. The dataset contains information about customers such as their age, gender, annual income, and spending score. The goal of this project is to cluster the customers based on their purchasing behavior and demographic characteristics.

By employing the K-Means clustering technique, we have effectively partitioned the data into various subgroups, predicated upon a diversity of distinct features. Subsequently, the management of the mall is able to effectively concentrate their efforts on particular clusters that possess an average spending score, with the objective of maximising the overall profitability.

## Table Of Content
- Overview

- What is Customer Segmentation

- What is K-Means Algorithm

- Dataset

- Steps for Implementation

- K-means Algorithm

- Determining Optimal Clusters

## Overview
Customer Segmentation is one the most important applications of unsupervised learning. Using clustering techniques, companies can identify the several segments of customers allowing them to target the potential user base. In this machine learning project, we will make use of K-means clustering which is the essential algorithm for clustering unlabeled dataset.

## What is Customer Segmentation

Customer Segmentation is the process of division of customer base into several groups of individuals that share a similarity in different ways that are relevant to marketing such as gender, age, interests, and miscellaneous spending habits.

Companies that deploy customer segmentation are under the notion that every customer has different requirements and require a specific marketing effort to address them appropriately. Companies aim to gain a deeper approach of the customer they are targeting. Therefore, their aim has to be specific and should be tailored to address the requirements of each and every individual customer. Furthermore, through the data collected, companies can gain a deeper understanding of customer preferences as well as the requirements for discovering valuable segments that would reap them maximum profit. This way, they can strategize their marketing techniques more efficiently and minimize the possibility of risk to their investment.

## What is K-Means Algorithm
While using the k-means clustering algorithm, the first step is to indicate the number of clusters (k) that we wish to produce in the final output. The algorithm starts by selecting k objects from dataset randomly that will serve as the initial centers for our clusters. These selected objects are the cluster means, also known as centroids. Then, the remaining objects have an assignment of the closest centroid. This centroid is defined by the Euclidean Distance present between the object and the cluster mean. We refer to this step as “cluster assignment”. When the assignment is complete, the algorithm proceeds to calculate new mean value of each cluster present in the data. After the recalculation of the centers, the observations are checked if they are closer to a different cluster. Using the updated cluster mean, the objects undergo reassignment. This goes on repeatedly through several iterations until the cluster assignments stop altering. The clusters that are present in the current iteration are the same as the ones obtained in the previous iteration.

## Dataset
The dataset is aquired from kaggle and the link is given below :

https://www.kaggle.com/nelakurthisudheer/mall-customer-segmentation
The dataset consists of following five features of 200 customers:
- CustomerID: Unique ID assigned to the customer
-  Gender: Gender of the customer
-  Age: Age of the customer
-  Annual Income (k$): Annual Income of the customer
-  Spending Score (1-100): Score assigned by the mall based on customer behavior and spending nature.

## Steps for Implementation
- Import all necesssary Package

   import ----- from ------

  import -----

- Data Exploration

 customer_data=read.csv("/home/dataflair/Mall_Customers.csv")

 str(customer_data)

 names(customer_data)

 head(customer_data)

 summary(customer_data$Age)

- Statistical Analysis

     sd(customer_data$Age)

     summary(customer_data$Annual.Income..k..)

     sd(customer_data$Annual.Income..k..)

     summary(customer_data$Age)

- Visualizations

      Bar Plot

      a=table(customer_data$Gender)

      barplot(a,main="Using BarPlot to display Gender Comparision",

       ylab="Count",
       
       xlab="Gender",
       
       col=rainbow(2),
       
       legend=rownames(a))


       Pie Chart

        pct=round(a/sum(a)*100)

       lbs=paste(c("Female","Male")," ",pct,"%",sep=" ")

       library(plotrix)

       pie3D(a,labels=lbs,

       main="Pie Chart Depicting Ratio of Female and Male")

       Histogram

       hist(customer_data$Age,

       col="blue",

       main="Histogram to Show Count of Age Class",

        xlab="Age Class",
        ylab="Frequency",
        labels=TRUE)

  ## Analysis

        Analyzing the annual income of the customers through the Histogram

        summary(customer_data$Annual.Income..k..)

        hist(customer_data$Annual.Income..k..,

        col="#660033",

         main="Histogram for Annual Income",
         xlab="Annual Income Class",
         ylab="Frequency",
         labels=TRUE)

  ## Density plot

        Density Plot
        plot(density(customer_data$Annual.Income..k..),

        col="yellow",

        main="Density Plot for Annual Income",
        xlab="Annual Income Class",
        ylab="Density")
        polygon(density(customer_data$Annual.Income..k..),
        col="#ccff66")


       Analyzing Spending Score of the Customers with the help of BoxPlot
       summary(customer_data$Spending.Score..1.100.)

       Min. 1st Qu. Median Mean 3rd Qu. Max. 
      ## 1.00 34.75 50.00 50.20 73.00 99.00

      boxplot(customer_data$Spending.Score..1.100.,
      horizontal=TRUE,
      col="#990000",
      main="BoxPlot for Descriptive Analysis of Spending Score")

  ##K-means Algorithm

  - We specify the number of clusters that we need to create.
  - The algorithm selects k objects at random from the dataset. This object is the initial cluster or mean.
  - The closest centroid obtains the assignment of a new observation. We base this assignment on the Euclidean Distance between object and the centroid
  - k clusters in the data points update the centroid through calculation of the new mean values present in all the data points of the cluster. The kth cluster’s centroid has a - - Length of p that contains means of all variables for observations in the k-th cluster. We denote the number of variables with p.
  - Iterative minimization of the total within the sum of squares. Then through the iterative minimization of the total sum of the square, the assignment stop wavering when we - - Achieve maximum iteration. The default value is 10 that the R software uses for the maximum iterations.

       

