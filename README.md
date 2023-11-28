Project Title

Assignment #5
Create a GitHub repository 

Short description
The first step is to load the data into a pandas DataFrame. 
This is done using the pd.read_csv() function, which reads a CSV file and converts it into a DataFrame.

Prerequisites

- Install Python 3.0
- Pandas Libariy

Installing

- Anaconda Jupiter notebook

Running the Tests

Please note that the use of SET SQL_SAFE_UPDATES=0 should be used with caution,
as it can potentially lead to unintended updates if not used carefully. 
It's essential to ensure that you are not making updates that could harm your data unintentionally when this mode is disabled.

Breakdown of Tests

main1.py:
To calculate the average global sales before and after 2005. 
This is done using boolean indexing to filter the rows of the DataFrame that meet the specified conditions,
and then calling the mean() function on the ‘Global_Sales’ column of the filtered DataFrame.After calculating the averages,
we compare them and store the result in a dictionary along with the averages (rounded to two decimal places). 
The dictionary key ‘Which one is higher?’ corresponds to whether the average global sales were higher before or after 2005, and the keys ‘Before 2005’ and ‘After 2005’ correspond to the calculated averages.

main2.py:
first ,we added a new ‘period’ column and initialized it with an empty string. 
Pandas provides the loc function which allows access and update rows of the DataFrame that meet certain conditions.
This function is used to update the ‘period’ column for rows where ‘Year’ is less than 2010 and for rows where ‘Year’ is greater than or equal to 2010. 
Finally the data frame is printed to view the updated dataset

Deployment

Run the main1.py file
Run the main2.py file

Here is a template

main1.py:
avg_before2005 = df[df['Year'] < 2005]['Global_Sales'].mean()
avg_after2005 = df[df['Year'] >= 2005]['Global_Sales'].mean()
result = {
    'Which one is higher?': 'After 2005 is bigger' if avg_before2005 < avg_after2005 else 'Before 2005 is bigger',
    'Before 2005': round(avg_before2005, 2),
    'After 2005': round(avg_after2005, 2)
}
print(result)

main2:
# Add a new column 'period' to the DataFrame
df['period'] = ''
# Update the 'period' column based on the condition
df.loc[df['Year'] < 2010, 'period'] = 'pre-2010'
df.loc[df['Year'] >= 2010, 'period'] = 'post-2010'
# Print the updated DataFrame
df

Author

Paras Chugh

License

Version 1.0
