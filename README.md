# Pup Inflation: Analyzing Tweets

## Problem Statement

The goal of this analysis is to determine if there has been grade inflation on the @dog_rates Twitter account, which rates the cuteness of users' dog pictures. We will analyze the data collected from the @dog_rates feed to investigate if there has been a significant increase in the ratings given to the dog pictures over time.

## Approach and Methods

1. **Data Loading and Preparation**

   - Load the data from the provided CSV file, "dog_rates_tweets.csv", into a DataFrame using Pandas.
   - Identify tweets that contain a rating by searching for ratings in the form of "X/10" and extract the numeric rating values.
   - Exclude tweets that do not contain a rating to focus only on the rating data.
   - Remove outliers by excluding rating values that are unrealistically large, such as ratings larger than 25/10.
   - Convert the "created_at" column to a datetime value if it is stored as a string. This can be done by using the `pd.to_datetime` function or specifying the `parse_dates` argument while loading the CSV file.

2. **Data Visualization**

   - Create a scatter plot of the date versus the rating to visualize the distribution of ratings over time.
   - This plot will provide an overview of the data and help identify any trends or patterns in the ratings.

3. **Linear Fitting**

   - Perform a linear regression analysis on the data to determine if there is a best-fit line that represents the overall trend in the ratings.
   - Use the `scipy.stats.linregress` function to calculate the slope and intercept of the best-fit line.
   - To perform the linear regression, convert the datetime values in the "created_at" column to timestamps using a custom function `to_timestamp`.
   - Apply the `to_timestamp` function to the "created_at" column either using the `apply` method or by directly passing the column to the function.
   - Calculate the linear regression parameters and obtain the slope and intercept for the best-fit line.

4. **Analysis and Conclusion**

   - Analyze the slope of the best-fit line to determine if there is evidence of grade inflation over time.
   - If the slope is significantly positive, it suggests that there has been an increase in the ratings given to the dog pictures over time, indicating grade inflation.
   - If the slope is close to zero or negative, it suggests that there has not been a significant increase in the ratings, indicating no grade inflation.
   - Draw conclusions based on the analysis and present the findings in a clear and concise manner.

The analysis is conducted in a Jupyter notebook named "dog-rates.ipynb". The notebook loads the data from the provided CSV file, performs the necessary data preparation steps, visualizes the data using scatter plots, and conducts a linear regression analysis to determine the presence of grade inflation. The conclusions are presented based on the analysis conducted.
