# Assignment-1
Q NO1: Write a function called proportion_of_education which returns the proportion of children in the dataset who had a mother with the education levels equal to less than high school (<12), high school (12), more than high school but not a college graduate (>12) and college degree.
Ans: First we will create a function that will read the cvs file containing data on children's health and returns a dictionary with the proportion of children with different levels of education in their household. By using the command 'pd.read_csv()' Then The function calculates the proportion of children in the dataset with each level of education by calling the 'value_counts()' which counts the number of occurrences of each unique value in the column and returns a pandas Series object with the counts. The normalize=True parameter is used to convert the counts to proportions, so that the sum of all proportions is 1. The resulting proportions are stored in a dictionary called EDUC1_dict, with education levels as keys and proportion as values.The function returns the EDUC1_dict dictionary.The assertions at the end of the code test that the function returns a dictionary with four items, where the keys are the expected education levels and the values are the expected proportions. The assertions also test that the function returns a dictionary object of the expected type.

Question 2: Let's explore the relationship between being fed breastmilk as a child and getting a seasonal influenza vaccine from a healthcare provider. Return a tuple of the average number of influenza vaccines for those children we know received breastmilk as a child and those who know did not.
ANS: The given code reads data from a CSV file named "NISPUF17.csv" using the pandas library and then computes the average number of influenza doses for two groups of people based on whether they received a flu shot during the survey period.

The first line of the code defines a function named average_influenza_doses

The second line of the code imports the pandas library as pd

The third line of the code reads the CSV file "NISPUF17.csv" using the read_csv method of pandas and stores the resulting DataFrame in a variable named df

The fourth line of the code creates a new DataFrame named df1 that includes only the records from df where the value of the "CBF_01" column equals 1. The "CBF_01" column is a binary variable that indicates whether the person received a flu shot during the survey period. A value of 1 indicates that the person received a flu shot, while a value of 2 indicates that the person did not receive a flu shot.

The fifth line of the code creates a new DataFrame named df2 that includes only the records from df where the value of the "CBF_01" column equals 2. This group includes people who did not receive a flu shot.

The sixth line of the code computes the mean of the "P_NUMFLU" column for df1 and df2 using the mean method of pandas. The "P_NUMFLU" column represents the number of influenza doses the person received during the survey period.

The seventh line of the code returns a tuple containing the mean of the "P_NUMFLU" column for df1 and df2. This tuple contains two values, the mean of df1 and the mean of df2

Therefore, the average_influenza_doses function calculates and returns the average number of influenza doses for people who received a flu shot (group df1) and those who did not receive a flu shot (group df2).

Question 3: It would be interesting to see if there is any evidence of a link between vaccine effectiveness and sex of the child. Calculate the ratio of the number of children who contracted chickenpox but were vaccinated against it (at least one varicella dose) versus those who were vaccinated but did not contract chicken pox. Return results by sex.
This function should return a dictionary in the form of (use the correct numbers):
{"male":0.2,
"female":0.4}
ANS: The function first imports the pandas library, which is a library used for data manipulation and analysis.
The function then reads in a CSV file named "NISPUF17.csv" and stores it as a pandas DataFrame called df.
It selects only the columns of interest from the DataFrame, which are "SEX", "HAD_CPOX", and "P_NUMVRC".
It removes any rows containing missing values using the dropna method.
It filters out any rows where P_NUMVRC is equal to 0, meaning that the person did not receive any doses of the chickenpox vaccine.
It then creates two new DataFrames, one for males and one for females, using boolean indexing based on the "SEX" column.
For each gender, it calculates the ratio of the number of people who had chickenpox (indicated by the value 1 in the "HAD_CPOX" column) to the number who did not (indicated by the value 2 in the "HAD_CPOX" column), but only for those who received at least one dose of the vaccine (indicated by P_NUMVRC >= 1).
The function then returns a dictionary with two keys, "male" and "female", whose values are the respective ratios calculated above.
Finally, the assertion statement checks that the returned dictionary contains exactly two items, one for males and one for females.
Question 4:A correlation is a statistical relationship between two variables. If we wanted to know if vaccines work, we might look at the correlation between the use of the vaccine and whether it results in prevention of the infection or disease [1]. In this question, you are to see if there is a correlation between having had the chicken pox and the number of chickenpox vaccine doses given (varicella).
##Some notes on interpreting the answer. The had_chickenpox_column is either 1 (for yes) or 2 (for no), and the num_chickenpox_vaccine_column is the number of doses a child has been given of the varicella vaccine. A positive correlation (e.g., corr > 0) means that an increase in had_chickenpox_column (which means more no’s) would also increase the values of num_chickenpox_vaccine_column (which means more doses of vaccine). If there is a negative correlation (e.g., corr < 0), it indicates that having had chickenpox is related to an increase in the number of vaccine doses.

##Also, pval is the probability that we observe a correlation between had_chickenpox_column and num_chickenpox_vaccine_column which is greater than or equal to a particular value occurred by chance. A small pval means that the observed correlation is highly unlikely to occur by chance. In this case, pval should be very small (will end in e-18 indicating a very small number).

##[1] This isn’t really the full picture, since we are not looking at when the dose was given. It’s possible that children had chickenpox and then their parents went to get them the vaccine. Does this dataset have the data we would need to investigate the timing of the dose?

ANS: The function average_influenza_doses() reads in the data from a CSV file using pandas and then filters the data based on the value of the "CBF_01" column. The values of 1 and 2 in the "CBF_01" column indicate whether the child was born in the US or not, respectively. Two new dataframes are created: one for children born in the US (CBF_01 = 1) and one for children born outside the US (CBF_01 = 2). The function then calculates the mean number of influenza vaccine doses administered to children in each group using the "P_NUMFLU" column, which contains the number of flu vaccine doses administered to each child. Finally, the function returns a tuple with two values: the mean number of flu vaccine doses for children born in the US and the mean number of flu vaccine doses for children born outside the US.
