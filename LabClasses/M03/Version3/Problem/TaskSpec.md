[![GitHub watchers](https://img.shields.io/badge/tulip--lab-SIT742--CloudFirst-brightgreen)](../../../../README.md)
[![GitHub watchers](https://img.shields.io/badge/SIT742-Prac--Class-orange)](../../../M03-Exercises.md)

# Practice Lab M03 (Version 3)
## Data Acquisition and Data Source

Practice Lab M03 will focus on how to properly acquire and read the data with differnt formats by python libary such as numpy.

## To do

- Read the given data for required format;
- Using Numpy and Pandas to do the ETL for the data.


## Tasks 1 Data Acquisition and Data Source
### Task 1.1 Web Crawling on Deakin Professors
We first do a simple task on crawling the data from html -- the Deakin IT staff page. To do this, we need to understand the structure of the html as well as the web crawling library -- selenium or beautiful soup. In this task, please find all professors (Emeritus Professors, Professors and Associate Professors only) in Schoolf of IT and save it as csv

- print the content from the tables which contain the professors information
- store the professors' name and title into a new dataframe
- store the google scholar citation information into csv


### Task 1.2 Formating the dictionary
Task 1.2 After acquiring the dataframe for the html, let's first focus on the dictionary format -- which is the common used format while for semi-structure data in frontend development. A record in dictionary (one row in csv format) is now partitioned on column level. We will try to first convert the ```Professor_citation_informaton.csv``` to the in memory dictionary (removing 'na'). Then we will format the dictionary by only selecting the records (rows) with ```citation_all > 3000``` and ```citation_all < 10000``` and then store it as a json file.

- read the csv as pandas dataframe ```df_citation``` and save remove the 'na' from the ```df_citation``` and convert it to dictionary
- print the keys and also the unique value from the values in in each (k,v) pair
- print both keys and the length of the **unique value** from the values in each (k,v) pair
- filter the dictionary by selecting the records (rows) with```citation_all > 3000``` and ```citation_all < 10000```
- store the filtered result into json 

### Task 1.4 ETL with pandasql  
Now we have the parser and also have the json file, then next step for us is doing the ETL by using sql in python. 

- first run a select query for the dataframe
- transformation on the column 'citation_all' with conditions (given in notebook) 
- calculate the average value of calculate the average value of 'citation_all', 'citation_since2016' by group the Title

### Task 1.5 Pandasql vs Pandas
Could we do the similar ETL as task 1.4 in pandas? Such as group by the height and weight by having the average value of  'citation_all', 'citation_since2016'.

- create the aggregation by using pandas 
- convert citation_all and citation_since2016 to categorical data type by specific conditions (condition is given in notebook)

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
