# python_project_2021_Orsi_K
Python project for the Jan 2021 Code Louisville class

This project takes the Jefferson County Residential Real estate Sales data from the past 1 year and merges it with the Rental data (both from Flex.mls)
in order to find the best neighborhoods/zip codes to invest in to get the best return.

First I imported the Sales data and the rental data xls files and created 2 dataframes.

Since I was going to use the Age of the house as one of the datapoints I needed to clean up that column (in some cases they had the year built as age, or 999 or 9999). I cleared these in both files.

Next I removed the rental data from before 2019 so that I'm not using very old data, but still have enough to have a meaningful analysis.

Then I grouped the data by subdivision and calculated the average Sales price/SqFt and average age and average size for each subdivision. I did the same grouping for the Rental data with average monthly rental price per SqFt, average age, average size

Then I merged the 2 datasets by subdivision.
Calculated the relative variances for age and size and if the rental data was 50% more different from the Sales data I removed those lines (the comparison is no longer relevant).

Once I realized that this is way too granular I went and calculated the exact same steps only this time by Zip Code.

In the Zip Code data I sorted the line items by highest average Rental income per average Sales price ratio (both relative to SqFt, removing the size factor from the equation)

Then I took the top 5 best Zip Codes and saved it in a table.

I went back to my original Zip Code data and added house size categories to the table and grouped the data by zip code by size category (0 - 1000 SqFt, 1000 - 2000 SqFt, etc.)

Then for the best 5 zip codes I created charts with secondary y axis to demonstrate the "price of entry" to the market by SqFt (e.g. in Zip Code: 40212 a house of size between 1000 - 2000 SqFt cost an average of $58K and can potentially bring in an average rent income of $800 per month)
