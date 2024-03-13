# pandas-challenge

## This is the repo for Module 4 Challenge

The code for this challenge was completed with the material learned during class. I only used ChatGPT in order to convert some values to numeric data and when I encountered errors such as the FutureWarnings from pandas.

In the 'Scores by School Spending' section

`# I had to remove non-numeric characters and convert to numeric to avoid encountering with TypeError: '<' not supported between instances of 'int' and 'str' OR Value Error: "Unable to parse string "$628.00" at position 0"`
`school_spending_df['Per Student Budget'] = school_spending_df['Per Student Budget'].replace(r'[\$,]', '', regex=True).astype(float)`

FutureWarnings from pandas adding 'observed=False'

`#  Calculate averages for the desired columns.`
`#  I had to add "observed=False" in order to silence a FutureWarning from pandas and to mantain the current behavior of the 'groupby' function.`
`spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"], observed=False)["Average Math Score"].mean()`
`spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"], observed=False)["Average Reading Score"].mean()`
`spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"], observed=False)["% Passing Math"].mean()`
`spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"], observed=False)["% Passing Reading"].mean()`
`overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"], observed=False)["% Overall Passing"].mean()`

`print(spending_math_scores)`
`print(spending_reading_scores)`
`print(spending_passing_math)`
`print(spending_passing_reading)`
`print(overall_passing_spending)`
