# Anomaly-Detection
Data preparation:

I used Jupyter Notebook to read the excel file, and used Python programming to perform the necessary operations to find the anomalies.
I firstly imported the necessary libraries which are required in data analysis coding. Then, I read the file on Jupyter Notebook with the help of the pandas library.
I used the .info() and .describe() methods to check if there are any null values, and also what is the datatype of each attribute.
Since there are no null values and each attribute is of object datatype, the data did not require any cleaning from my side to find the anomalies. 

Analysis Strategy:

To understand the methodology, let us understand two methods that were used in this process.
.applymap() – This method helps to apply a function to a dataframe elementwise.
.isreal – This method is used to test element-wise whether it is a real number or not(not infinity or not Not a Number) and return the result as a Boolean array
.all() – This is used to check if all the items in the list are true.
The code line that was used to find the anomalies is as follows:
x = df[~df.applymap(np.isreal).all(1)]
Here, we’ve filtered out all the rows that don’t contain a real number, store the Boolean values and return the rows that fulfil this condition.
We then store this data in an excel sheet.


