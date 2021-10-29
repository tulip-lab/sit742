[![GitHub watchers](https://img.shields.io/badge/tulip--lab-SIT742--CloudFirst-brightgreen)](../../../README.md)
[![GitHub watchers](https://img.shields.io/badge/SIT742-Prac--Class-orange)](../../M02-Exercises.md)

# Practice Lab M02

In this prac, we will build on a project based on the USA baby name data. 
The data include those most popular names for babies born on each year in USA. 
This neat [data](http://www.socialsecurity.gov/OACT/babynames/#ht=0) is published by USA Social Security administration. 
We have quite similar data set from different states here in Australia. 

By the end this prac, we will be able to extract relevant information from multiple data files, and consolidate them into a single file. 
Base on these data, we can either print the data in specific format later, or feed them to other programs or systems as their input. 

The baby name data are in the following format:

| Year | Name | Gender | Count |
| --- | ----------- |----------- |----------- |
| 2000 | Jane |F|1903|
| 2000 | Michael |F|1993|
| 2002 | Ethan |F|3029|
| 2003 | Joshua |F|1021|
| ... | ... |..|...|

There are total 2 tasks and 7 sub-tasks in this practice. The first task on the **USA baby name** project is to perform read and write on multiple baby name data, i.e. read files on popular baby names, extract **name**  and **rank**, write the data fields into a file. you will be provided the dataset in txt format for multiple data files , which includes data on Year 2000, 2002, 2004, 2006 and 2008. 
As output,  these data need to be written into the summary file with requirements. In addition, to generalize the program so that it can apply to arbitrary filenames, in task 2, the above read and write will be coded into python function with multiple arguments.  
 

## Task1 Writing and Reading Text Files 
### Task 1.1
we will use open() method with nested for loop to read information from the single file or multiple files. 

Here is what should be written into the new file
| Year | Name | Gender | Count |
| --- | ----------- |----------- |----------- |
| 2000 | Jane |F|1903|
| 2000 | Michael |F|1993|
| 2002 | Ethan |F|3029|
| ... | ... |..|...|

### Task 1.2
We will use the fileinput method to read information from multiple files without nested for loop.


### Task 1.3
We will read and write all the txt files to new file in the given input path without manually adding filenames. 

### Task 1.4
We will read and write all the txt files to new file in the given input path without manually adding filenames, and also the writing will be done with specific format (format is given in notebook). 


Here is what is written into the new file

|Name | Count |
| --- | ----------- |
| Jane |1903|
| Michael |2930|
| ...|...|

### Task 1.5
We will read and write all the txt files to new file in the given input path without manually adding filenames, and also the start letter of the name is with requirements (requirements are given in notebook).


Here is what is written into the new file on condition of start letter with 'B'
|Name | Count |
| --- | ----------- |
| Ben |12|
| Brand |2930|
| ...|...|

### Task 1.6
We will read and write all the txt files to new file in the given input path without manually adding filenames, and also the start letter of the name is with requirements. Lastly, we will sort the names by count in desc order.

Here is what is written into the new file on condition of start letter with 'B'

|Name | Count |
| --- | ----------- |
|Bill|         219830|
|Bruce|     19821|
| ...|...|

### Task2: Design the Python function for extracting the names
### Task 2.1
We will write the function which could read the particular file and output new file with arguments.
The arguments should contain the input data path, the new file name, the gender and start letter.

