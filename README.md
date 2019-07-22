# BD-Prj-Yelp
Big data final project about Yelp data

Group Member: Jiaqi Chen, Haoning Liu, Xiaolu Li, Mengqi Li


## Data Introduction:
1. Data Source: Kaggle (link: )

2. Context
Yelp provide data for .... There're four Json files involing business, user, tip, review and check-in.

3. Size


4. Format
Json files.

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




## NLP

