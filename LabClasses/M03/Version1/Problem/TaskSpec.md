[![GitHub watchers](https://img.shields.io/badge/tulip--lab-SIT742--CloudFirst-brightgreen)](../../../../README.md)
[![GitHub watchers](https://img.shields.io/badge/SIT742-Prac--Class-orange)](../../../M03-Exercises.md)

# Practice Lab M03 (Version 1)
## Data Acquisition and Data Source

Practice Lab M03 will focus on how to properly acquire and read the data with differnt formats by python libary such as numpy.

## To do

- Read the given data for required format;
- Using Numpy and Pandas to do the ETL for the data.


## Tasks 1 Data Acquisition and Data Source
### Task 1.1 Reading parquet file
We first read the given data source **bank.parquet**. However, it is not in a standard readable format. The parquet file is in columnar storage format for efficient storage purpose (very common in cloud service scenario). Our goal in this task is to read this parquet file.

- read the parquet file by using pyarrow
- direct read by using pandas and save the data as ```df_```
- print the parquet file schema
- print the metadata for the parquet file
- convert the parquet file into table format and print it in dataframe type by using ``` table = parquet_file.read() ```
- print the table into dictionary format

### Task 1.2 Formating the dictionary
After having the dataframe for the given data, let's first focus on the dictionary format -- which is the common used format while for semi-structure data in frontend development.
We will try to format the dictionary by only selecting the records (rows) with age > 50 and age < 70 and then store it as a json file.

- print out all the keys and the length of the values in the given data dictionary
- print the keys and also the unique value from the values in in each (k,v) pair
- print both keys and the length of the **unique value** from the values in each (k,v) pair
- filter the dictionary by selecting the records (rows) with age > 50 and age < 70
- store the filtered result into json

### Task 1.3 Building the parser
After reading the data and also filter the dictionary, we finally have our json file and store it in our repo. However, if we need to regularly perform the similarly tasks for acquire the datasource, a parser is required. Could you write a parser function to contain the above parquet reading and dictionary filtering functionalities?

- write code for the parser to be able to read the parquet file and save it as json with condition

### Task 1.4 ETL with numpy 
Now we have the parser and also have the json file, then next step for us is doing the ETL by using numpy. Let's first understand the most important numpy operation -- Broadcasting. In this task, please use the numpy to add 10 to every age in 'newbank.json'.

- read the newbank.json into dataframe by using pandas
- convert the dataframe into numpy-- ```np_df``` and print the shape
- slicing the age from the ```np_df``` as ```np_df_age``` and print the shape
- use the ```np.broadcast``` to add 10 on each age and save the result as ```np_df_age_new```, also print the shape
- add the ```np_df_age_new``` back to ```np_df``` and save it as ```np_df_new```, also print the shape
- convert the numpy array to dataframe -- ```df_newbank_new``` and print the first 5 rows (give the new column a name as 'new_age' and make sure new column is on the first column)

### Task 1.5 Numerical vs Categorical 
Could we devide the numerical columns and categorical columns from original dataframe ```df_``` (from task 1.1)?

- slice the original dataframe ```df_``` by only selecting the numerical columns, save the new dataframe as ```df_num```
- slice the original dataframe ```df_``` by only selecting the categorical columns, save the new dataframe as ```df_cat```

### Task 1.6 (Advanced) Transforming the categorical data
Now we have divided the df_ into two part, numerical dataframe and categorical dataframe. For many big analysis, category data is not the best format to start with. The common way to deal category data is to transform it to one hot encode format (only with 1 and 0). Could you finish the one hot encode transforming for categorical dataframe by using the ```df_onehot = pd.get_dummies(s)```?

- write code for the one hot encode and print the dataframe
- combine the new onehot encode dataframe with numerical dataframe to obtain the full dataframe ```df_all```

## Tasks 2 Advanced Data Acquisition
### Task 2.1 Advanced numpy operation 1
In numpy, the euclidean distance could be calculated via
```
np.sqrt(np.sum(np.square(point1 - point2)))
```
point1 and point2 is the 1D array, please folllow the above calculation and build a function to calculate the euclidean distance for any two arrays from a given dataframe.

- define the funtion with name ```dist_func```
- calculate the distance from point1 to each dimension of point2 when point 2 is 2D array

### Task 2.2 Advanced numpy operation 2
Now, we will need to calculate the euclidean distance between each row and all the rows (let's include the current row at here), also we would like to save the distances into array for each row. To the end, you will have a distance matrix with shape of (n,n) where n is the total rows. We will use top 100 rows from ```df_all``` (task 1.6) as the input.

- write the code for the distance matrix
- find the index of the smallest distance for each row in the distance
- put the results into pandas dataframe and print the dataframe

