# BD-Prj-Yelp
Big data final project about Yelp restaurant review.

Group Member: Jiaqi Chen, Haoning Liu, Xiaolu Li, Mengqi Li

## Abstract
The objective is to apply the big data analytical concept and tools taught in Big data course to extract insightful analytics and help existing restaurant. We applied descriptive analysis, predictive analysis and sentiment analysis to this dataset.

## Introduction
Yelp is a local business directory and social networking reviews website. It enables customers to give companies ratings and reviews. Usually the review is brief text composed of a few lines with approximately 100 phrases. Often, a review defines different dimensions of a company and the user's experience with regard to those aspects.

## Explanation for changing the dataset
Originally, our group started from NYU Parking tickets. We conduct descriptive analysis of the dataset using Pyspark, S3 Hardoop. However, we didn't find an intereting aspect of this dataset to starting on modeling. Therefore, we decide to change the dataset. Currently, we are working onn Yelp restaurant review dataset.


## Data Introduction:
1. Data Source: Kaggle (link: )
These dataset contain a subset of Yelp’s businesses, reviews, and user data. It was originally put together for the Yelp Dataset Challenge
2. Context
Yelp provide data for .... There're four Json files involing business, user, tip, review and check-in.

3. Size


4. Format
Json files.

## Methods and Tools
R
Python
PySpark

Why PySpark?


## Data Cleaning Up Processing

1. Convert Json to CSV using R with a code example as following:

library(jsonlite)

file_name <- 'yelp_academic_dataset_tip.json'

tip<-jsonlite::stream_in(textConnection(readLines(file_name, n=1000000)),verbose=F)  # Adjust number of readLines with lenghth of each Json file.

length(tip)

write.csv(tip,"yelp_tip.csv",row.names = F)

2. Upload CSV files onto S3 bucket.

3. Load data from S3 and use Python to clean up 'text' columns, removing comma, quotation mark and \r\n from 'text'. Separate data between columns with comma and quotation mark and data between rows with \r\n.

4. Deal with null values for some important attributes.

5. Merge four data files together with buissness ID and user ID.



## Descriptive Analysis



## Logistic Model

We try to predict rating for each business ? on Yelp by reasonalbe attributes in data. Considering the distribution of rating scores, from 1 star upto 5 stars, we define no more than 3 stars as low rating and convert the number of stars into 0 and those with over 3 stars as high rating and convert it into 1. Thus we get the column for prediction named stars as boolean value.

### Model Processing
1. Select features as string attributes and numeric attributes.
2. Drop 134 rows with null values in stars column.
3. 
4. 
5.

### Model AUC
0.81

### Conclusion




## Sentiment Analysis
1.Data preprocessing
The majority of the reviews focuses on the positive sides -- intuitively, people tend to leave reviews when they feel great about their experience. Contradictory, the number of extremely negative reviews (1 star) also overwhelm the number of neutral reviews (2 or 3 stars).



## Conclusions



## Challenges and Solutions
1. Data transfering from Json to CSV
2. Read in data with text columns in a neat format
3. Upload data onto S3 bucket from local cost long time
4. Code for model trainning and testing doesn't respond due to the large size of data
....

