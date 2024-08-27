# UK JOBS DATA PARSING AND WRANGLING


##### Libraries used:
* pandas
* re
* numpy
* seaborn
* matplotlib
* ElementTree

[The first notebook](../main/Jobs-Data-Parsing-and-Cleaning.ipynb) goal is to parse the jobs data in a provided ***xml file*** that is collected from multiple jobs websites in UK such as 'totaljobs.com', 'jobsite.co.uk'... from 2012 to 2014 into a dataset following the format: 

Column         | Description
---------------|-----------------------------------------------------------------------------------------------------
Id             | [Integer] 8 digit integer. Note you should not change the values of the Id.
Title          | [String] If there is no title information, the value should be ‘non-specified’
Location       | [String] If there is no location information, the value should be ‘non-specified’.
Company        | [String] If there is no company information, the value should be ‘non-specified’.
ContracType    | [String] It could be ‘full_time’, ‘part_time’ or ‘non-specified’.
ContractTime   | [String] It could be ‘permanent’, ‘contract’ or ‘non-specified’.
Category       | [String] There are 8 possible categories: ‘IT Jobs’, ‘Healthcare & Nursing Jobs’, ‘Engineering Jobs’, ‘Accounting & Finance Jobs’, ‘Sales Jobs’, ‘Hospitality & Catering Jobs’, ‘Teaching Jobs’, ‘PR, Advertising & Marketing Jobs’.8 digit Id of the job advertisement
Salary         | [Float] All the values need to be expressed to two decimal places, e.g., 80000.25. Also, all salary values must be valid float numbers and not null.
OpenDate       | [Datetime] All the values need to be in the datetime format, yyyy-mm-dd hh:mm:ss,
CloseDate      | [Datetime] All the values need to be in the datetime format, yyyy-mm-dd hh:mm:ss,e.g.,
SourceName     | [String] If there is no source information, the value should be ‘non-specified’.

Each variables are handled and cleaned so that they stricly follow the required format. Other data problems are also put into consideration and proper methods for each are applied.


[The second notebook](../main/Jobs-Data-Integration.ipynb) goal is merging the cleaned dataset with new dataset that are from 'www.jobhuntlisting.com'. 
However, the dataset is in different format, schematic mapping is applied to resolve the conflict before merging. 
Data conflicts are also considered and handled.


Output of this project includes:
- [**cleaned_dataset1.csv**](../main/cleaned_dataset1.csv): A csv of the cleaned following the requirements dataset.

- [**errors_list.csv**](../main/errors_list.csv): A csv that stores all the modification as cleaning attempts. Under the following format:

Column         | Description
---------------|-----------------------------------------------------------------------------------------------------
indexOfdf      | the index of the record/row in the original dataset. If the data issue involves all rows, put “ALL”.
Id             | the id of the job advertisement that has the data issue. If the data issue involves all job records, put “ALL”.
ColumnName     | The name(s) of the column that the data issue locates. /n ● If the data issue involves more than one column, you can put multiple column names separated by a comma, e.g., “Cloname1,Colname2,Colname3”. /n ● If the data issue involves all columns, just put “ALL”.
Original       | The original value of the cell. If the data issue involves all rows with different cell values, just put “ALL”.
Modified       | The modified value of the cell. If the data issue involves all rows with different modified cell values, just put “ALL”.
ErrorType      | The type of errors, for example, Missing Values, Violation of Integrity Constraint, Outliers, or any other errors you found.
Fixing         | Describe how did you fix this problem


- [**dataset_integrated.csv**](../main/dataset_integrated.csv): A csv of the result dataset from integration of the cleaned dataset and the additional dataset.


*Assignment 2 of RMIT COSC3015 Advanced Programming for Data Science*
