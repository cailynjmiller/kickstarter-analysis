# Kickstarting with Excel

## Overview of Project

### Purpose
Louise recently launched a campaign for her play, Fever, and reached close to her fundraising goal in a short amount of time. She wants to see the success rates of other plays based on their luanch dates and funding goals to uncover trends.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
I created a pivot table that outlines the amount of campaigns for each outcome (successful, failed, and canceled) based on the month the campaign was launched, filtered on the parent category to only display theater campaigns. For this view, I placed "Outcomes" in the columns and values, "Date Created Coversion" to rows, and "Parent Category" to filters, filtered on theater. I wanted this table to be able to be filtered by year to have the ability to see the trends for only a certain time period if desired, so, I created a "Years" column in the dataset based off of the "Date Created Conversion" field and placed the new "Years" field  in the filters for the pivot table. In order to vizualize this data, I created a line chart which displayed the amount of successful, failed, and cancelled campaigns with the months on the x-axis.
![Theater_Outcomes_vs_Launch](https://github.com/cailynjmiller/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
I created a table to display the amount of campaigns in each outcome based on the funding goals with the outcomes in the columns ("Number Successful, etc.) and ranges of funding goals in the rows ("1000 to 4999", etc.). I used the COUNTIFS function in each cell to count the amount of entries where the subcategory is "play", the outcome is the same as the column heading, and the goal range is the same as the row in the Kickstarter dataset. To the right of the columns, I created a "Total Projects" column where I used the SUM function to add the projects in each category for the particular funding goal range. To the right of the total column, I created 3 more columns for the percentage of the total for each outcome ("Percentage Successful", etc.) where I used a function to divide the number of that outcome by the total for the particular funding goal range and changed the format to be a percentage.
In order to visualize this data, I created a line chart to display the percentages of successful, failed, and canceled campaings based on the funding goal range. There are 3 lines for each outcome, the funding goals on the x axis, and the percentage of total on the y axis.
![Outcomes_vs_Goals](https://github.com/cailynjmiller/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered
A challenge that I faced while creating the pivot table for outcomes based on launch date was ensuring that the rows displayed months for the date instead of years and quarters. This is because when I dragged the "Date Created Converstion" field to rows, it automatically created two fields for "Years2" (titled Years2 because there was already a years column) and "Quarters". Once I unchecked "Years2" and "Quarters" from the fields list, it displayed months as I intended.
A challenge that I faced while creating the table for oucomes based on funding goals was not adding enough criteria to the COUNTIFS function and isntead counting on filtering in the Kickstarter dataset. I originally used the COUNTIF function and only had it check for the criteria where column F = "outcome" and filtered the dataset to only plays and filtered the funding goal range. After filling out a couple rows of my table, I found that the numbers were the same. This was because, even though I had filtered the dataset, by referencing the range F:F, it would count all entries regardless of the filters in the dataset. To fix this problem, I used the COUNTIFS function to include more than one criteria and included criteria for outcomes, funding goals, and subcatgegory.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
One conclusion I drew from the analysis of outcomes based on launch date was that theater campaigns launched in the months between May and July had a higher probability of being successful as opposed to those launched in other months. I drew this conclusion because, when refencing the line graph, the gap between successful and failed campaings was greatest in May-July.
Another conclusion I drew from this analysis was the failure rate was greatest in the months October through December, even though the success rate is always greater than the failure rate. In fact, in December it appears that probabilty of failure is barely smaller than the probability of success. I drew this conclusion because the gap between successful and failed campaigns was the smallest in the months October-December.

- What can you conclude about the Outcomes based on Goals?
As the fundraising goal gets higher, the success rate gets lower and the failure rate gets higher. I concluded this by analyzing the line graph and noticed that, overall, the success rate trends down as the goals get higher and, consequently, the failure rate trends up. However, there is an exception in the funding goal range from 35,000 to 45,000, where the success rate bounces up, but immediately shoots back down greater than 45,000.

- What are some limitations of this dataset?
One limitation of the dataset is that there is not much data before the year 2014, the numbers of entries dramatically decline as you look at earlier years. Having more historical data would make our analyses more accurate.
Another limilation of the dataset is how the goals and pledged amounts are not weighted based on the currency. For example, british pound is worth more than the us dollar. This provides a limitation when analyzing goals and pledged amounts because an entry in one currency could appear higher than that of one with another currency, but that could not be the case.

- What are some other possible tables and/or graphs that we could create?
A line graph that shows the percentage of outcomes based on the duration of the campaign. To do this, you would create a new column for the amount of days for each campaign. The number of days would be displayed on the x-axis in ranges (1-30 days, 30-60 days, etc.), and the percentage of total on the y-axis. There would be 3 lines for each outcome, successful, failed, and canceled. This chart would be useful to analyze any trend there may be between the duration of the campaign and success rate.
