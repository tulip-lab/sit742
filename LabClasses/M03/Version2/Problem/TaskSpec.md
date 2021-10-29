[![GitHub watchers](https://img.shields.io/badge/tulip--lab-SIT742--CloudFirst-brightgreen)](../../../../README.md)
[![GitHub watchers](https://img.shields.io/badge/SIT742-Prac--Class-orange)](../../../M03-Exercises.md)

# Practice Lab M03 (Version 2)
## Data Acquisition and Data Source

Practice Lab M03 will focus on how to properly acquire and read the data with differnt formats by python libary such as numpy.

## To do

- Read the given data for required format;
- Using Numpy and Pandas to do the ETL for the data.


## Tasks 1 Data Acquisition and Data Source
### Task 1.1 Reading parquet file
We first read the given data source **player.parquet**. However, it is not in a standard readable format. The parquet file is in columnar storage format for efficient storage purpose (very common in cloud service scenario). Our goal in this task is to read this parquet file.

- read the parquet file by using pyarrow
- direct read by using pandas and save the data as ```df_```
- print the parquet file schema
- print the metadata for the parquet file
- convert the parquet file into table format and print it in dataframe type by using ``` table = parquet_file.read() ```
- print the table into dictionary format

### Task 1.2 Formating the dictionary
After having the dataframe for the given data, let's first focus on the dictionary format -- which is the common used format while for semi-structure data in frontend development.
We will try to format the dictionary by only selecting the records (rows) with Height(CM) > 165 and Height(CM) < 175 and then store it as a json file.

- print out all the keys and the length of the values in the given data dictionary
- print the keys and also the unique value from the values in in each (k,v) pair
- print both keys and the length of the **unique value** from the values in each (k,v) pair
- filter the dictionary by selecting the records (rows) with Height(CM) > 165 and Height(CM) < 175
- store the filtered result into json 

### Task 1.3 Building the parser
After reading the data and also filter the dictionary, we finally have our json file and store it in our repo. However, if we need to regularly perform the similarly tasks for acquire the datasource, a parser is required. Could you write a parser function to contain the above parquet reading and dictionary filtering functionalities?

- write code for the parser to be able to read the parquet file and save it as json with condition
- read the json file as pandas dataframe ```df_newplayer```

### Task 1.4 ETL with pandasql  
Now we have the parser and also have the json file, then next step for us is doing the ETL by using sql in python. 

- first run a select query for the dataframe
- transformation on the column 'Dribbling' with conditions for ```df_newplayer```: if ```0<dribbling<=27``` then 'low'; ```27<dribbling<=61``` then 'medium'; ```61<dribbling<=73``` then 'good'; ```73<dribbling<=100``` then 'excellent'. 
- calculate the average value of 'Crossing', 'Finishing', 'HeadingAccuracy', 'ShortPassing','Dribbling', 'Curve','FKAccuracy', 'LongPassing', 'BallControl' by grouping the height and weight

### Task 1.5 Pandasql vs Pandas
Could we do the similar ETL as task 1.4 in pandas? Such as group by the height and weight by having the average value of 'Crossing', 'Finishing', 'HeadingAccuracy', 'ShortPassing','Dribbling', 'Curve', 'FKAccuracy', 'LongPassing', 'BallControl'.

- create the aggregation by using pandas 
- convert BallControl and Dribbling to categorical data type by specific conditions (condition is given in notebook)

### Task 1.6 (Advanced) Transforming the categorical data
Now we have the dataframe on both numerical and categorical datatype. For many big analysis, category datatype is not the best format to start with. The common way to deal category datatype is to transform it to one hot encode format (only with 1 and 0). Could you finish the one hot encode transforming for categorical column by using the ```df_onehot = pd.get_dummies(s)```?

- write code for the one hot encode and print the dataframe for categorical column
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
