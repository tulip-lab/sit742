# Practice Lab M04 (Version 3)
## Data Wrangling and Exploratory Data Analysis

Practice Lab M04 will focus on how to do the data wrangling and exploratory data analysis on big data technologies such as pyspark

## To do

- Use pyspark to perform data wrangling
- Conduct the exploratory data analysis with visualization.


## Tasks 1 Data Wrangling on Pyspark
### Task 1.1 Reading parquet file
We first read the given data source **magic.parquet**. However, it is not in a standard readable format. The parquet file is in columnar storage format for efficient storage purpose (very common in cloud service scenario). Our goal in this task is to read this parquet file.

- read the parquet file by using pyspark
- print the pyspark dataframe schema

### Task 1.2 Pyspark operation
After having the dataframe for the given data in pyspark, let's do some wrangling operation by using pyspark

- filter the data on column fWidth where fWidth > 50
- filter the data on column fWidth where fWidth > 50 and fWidth < 70, then print the statistic information of 'fSize' (using describe())
- filter the data on column fWidth where fWidth  > 60 and print the statistic information of 'fSize' (using describe())

### Task 1.3 Normalization and Standardization
After reading the data and also filter the data, we will sometime need to perform the normalization and standardization on the data.

- write code for the normalizing the fWidth on min max scaler and create new column 'scaled_fWidth 
- write code for normalizing multiple column in the same time 
- write code for the standardization for the fWidth and create new column 'standardized_fWidth ', save the dataframe called 'df_stand'

### Task 1.4 Pyspark dataframe join
Now we have to join the dataframe. Particularly, we want to join the original dataframe with 'df_stand'.
Firstly, we need to find a ID to join

- Using windowfunction to create rownumber on both original dataframe and 'df_stand'
- Joining the two dataframe on rownumber and save the final joined dataframe as 'dataframe_pd'

## Task 2 Exploratory Data Analysis
### Task 2.1 Vislauzation for checking distribution 
Now we want to plot the histogram to check the distribution of 'fLength' from 'dataframe_pd'

- Using ```sns.distplot``` to plot the histogram for fLength
- Using pandas dataframe ```hist()``` function to plot the distributoins for all the numerical columns

### Task 2.2 Boxplot 
Now we have to draw the boxplot to check the distribution on discrete columns

- Discrete the 'fWidth', 'fLength', 'fAlpha' and create new columns (bin is given in notebook)
- Using ```sns.countplot``` to plot the boxplot for discrete 'fLength'
- Drawing the ```sns.countplot``` with x on discrete 'fLength' and y on the 'fConc' (numerical format)

### Task 2.3 (Advanced) Heatmap visualization
We want to group the discrete  'fWidth', 'fLength' to obtain the count for each. However we want to exclude the 'fLength' on bin 1

- Create the group by with pandas
- Draw the count into heatmap by using ```sns.heatmap()```
