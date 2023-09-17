# Module 3 Challenge – Python  
## PyCitySchools Analysis  
### For this assignment, we are trying to find:  
- District Summary  
- School Summary  
- Highest-Performing Schools by Percentage of Overall Passing  
- Lowest-Performing Schools by Percentage of Overall Passing  
- Math Scores by Grade  
- Reading Scores by Grade  
- Scores by School Spending  
- Scores by School Size  
- Scores by School Type  
- Write a cohesive summary of the analysis  

### The script will follow the below process for data analysis:  
> 1. Import the necessary library for CSV files and file handling using the `import` 
function.  
> 2. Define the file path for the raw data file using `pd.read_csv()` and merge the data 
into a single dataset by column name using `pd.merge(df1, df2, on='COLUMN NAME)`.  
> 3. Calculate the District Summary by finding the number of schools and students using
`.nunique()`, the total budget using `.sum()`, the average math and reading using 
`.mean()`, and the percentage of students who passed. Then create a snapshot of the 
district's key metrics in a DataFrame.  
> 
>> ```py
>> district_summary = pd.DataFrame({
>>     "Total Schools": [school_count],
>> <...>
>>     "% Overall Passing": [overall_passing_rate]
>> })  
>> ```  
>  
> 4. Calculate the School Summary by finding the count for each type of school and the 
number of students per school using `.value_counts()`, total school budget and per 
capita spending per school, average test scores per school, and percentage passing. 
Then create a snapshot of the school’s key metrics in a DataFrame. For School Type, use 
`.set_index()` to index by `school_name` column making it the row labels.  
>  
>> ``` py
>> per_school_summary = pd.DataFrame({
>>     "School Type": school_data.set_index("school_name")["type"],
>>     "Total Students": per_school_counts,
>> <...>
>>     "% Overall Passing": overall_passing_rate
>> })
>> ```
>  
> 5. Find the Highest-Performing and Lowest-Performing Schools by using the 
`.sort_values()` set `ascending=` to False or True.  
> 6. Find the Math and Reading Scores by Grade by first separating the data by grade, 
then `.groupby()` `school_name` and take the mean of the `math_score` column for 
each. Then combine them into one DataFrame.  
> 7. Find the Scores by School Spending, Scores by School Size, and Scores by School 
Type by first establishing the bins, finding the averages, and then using `pd.cut` to 
categorize spending based on the bins. AskBCS Learning Assistant suggested, then, assembled into a DataFrame.  
The below code needs to be written with the `right` parameter, due to the value of `bin` being intervals.
>  
>> `pd.cut(per_school_capita, spending_bins, labels=spending_labels, right=False)`. 
>  

This data suggests that school type, per-student budget, and size affect academic 
performance. Specifically, charter schools perform better than district schools, lower per-student 
budgets improve performance, and smaller schools perform better.  

## External Links:
[Unique values](https://sparkbyexamples.com/python/pandas-count-unique-values-in-column/)  
[Index Explanation](https://sparkbyexamples.com/python/pandas-index-explained-with-examples/)  
[Sorting Values](https://sparkbyexamples.com/pandas/pandas-dataframe-sort_values/)  
[Cut Function](https://pandas.pydata.org/docs/reference/api/pandas.cut.html)
