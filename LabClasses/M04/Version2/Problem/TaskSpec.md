# Practice Lab M04 (Version 2)
## Data Wrangling and Exploratory Data Analysis

Practice Lab M04 will focus on how to do the data wrangling and exploratory data analysis on big data technologies such as pyspark

## To do

- Use pyspark to perform data wrangling
- Conduct the exploratory data analysis with visualization.


## Tasks 1 Data Wrangling on Pyspark
### Task 1.1 Reading parquet file
We first read the given data source **player.parquet**. However, it is not in a standard readable format. The parquet file is in columnar storage format for efficient storage purpose (very common in cloud service scenario). Our goal in this task is to read this parquet file.

- read the parquet file by using pyspark
- print the pyspark dataframe schema

### Task 1.2 Pyspark operation
After having the dataframe for the given data in pyspark, let's do some wrangling operation by using pyspark

- filter the data on column BallControl where BallControl > 50
- filter the data on column BallControl where BallControl > 50 and BallControl < 70, then print the statistic information of BallControl (using describe())
- filter the data on column LongPassing where LongPassing > 60 and print the statistic information of BallControl  (using describe())

### Task 1.3 Normalization and Standardization
After reading the data and also filter the data, we will sometime need to perform the normalization and standardization on the data.

- write code for the normalizing the Height on min max scaler and create new column 'scaled_Height'
- write code for normalizing multiple column in the same time 
- write code for the standardization for the Height and create new column 'standardized_Height', save the dataframe called 'df_stand'

### Task 1.4 Pyspark dataframe join
Now we have to join the dataframe. Particularly, we want to join the original dataframe with 'df_stand'.
Firstly, we need to find a ID to join

- Using windowfunction to create rownumber on both original dataframe and 'df_stand'
- Joining the two dataframe on rownumber and save the final joined dataframe as 'dataframe_pd'

## Task 2 Exploratory Data Analysis
### Task 2.1 Vislauzation for checking distribution 
Now we want to plot the histogram to check the distribution of 'Height' from 'dataframe_pd'

- Using ```sns.distplot``` to plot the histogram for Height
- Using pandas dataframe ```hist()``` function to plot the distributoins for all the numerical columns

### Task 2.2 Boxplot 
Now we have to draw the boxplot to check the distribution on discrete columns

- Discrete the 'LongPassing','Acceleration','SprintSpeed','Agility','Reactions' and create new columns (bin is given in notebook)
- Using ```sns.countplot``` to plot the boxplot for discrete 'LongPassing'
- Drawing the ```sns.countplot``` with x on discrete 'LongPassing' and y on the 'dribbling' (numerical format)

### Task 2.3 (Advanced) Heatmap visualization
We want to group the discrete 'LongPassing', 'Acceleration' to obtain the count for each. However we want to exclude the 'LongPassing' on bin 1

- Create the group by with pandas
- Draw the count into heatmap by using ```sns.heatmap()```
