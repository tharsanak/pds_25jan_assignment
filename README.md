# Assignment Reflection
## What was easy
Part 1 became much easier once I understood how Python reads files using the `open()` function. After I got `csv_rows` working properly, the other functions felt like natural extensions of it. Each function built on the previous one, so once `csv_rows` and `csv_cols` were correct, writing `table_min_max_median` was straightforward. The median calculation also became clearer once I separated the odd and even cases.

In Part 2, I enjoyed exploring the dataset. Merging the two CSV files using the timestamp column worked well, and the graphs made the patterns easy to see. The difference between weekday and weekend usage became very clear when I looked at the hourly plot.

## What was hard
The most difficult part of Part 1 was dealing with missing values. The dataset used a dash to show missing entries, which caused errors when I tried to convert the values to floats. I solved this by using a try/except block, so anything that could not be converted was left as text.

In Part 2, the timestamp column was confusing at first. Pandas read the dates in US format (month/day/year), but the data was actually in UK format (day/month/year). This led to incorrect dates until I used `dayfirst=True` in `pd.to_datetime()`.

## Strengths of my approach
My functions in Part 1 were well organised and built on each other, which made the code easier to follow and test. I also added comments and tested each function with different inputs, including edge cases like missing values and small row ranges.

For Part 2, I used the IQR method to find outliers because the data was right-skewed, so it was a better choice than the z-score method. I also used a one-tailed t-test because my initial exploration suggested a clear direction: weekday usage would be higher than weekend usage.

## Weaknesses and possible improvements
`csv_rows` reads the whole file before slicing, so it is not very efficient for large files. A better approach would be to stop reading once the required rows have been reached.

`print_min_max_median` works well, but it could be improved by adding an option to save the results as a CSV or HTML file.

In Part 2, I mainly focused on temperature and day type. It would be interesting to look at how wind speed or humidity affect bike usage, as they might reveal other useful patterns.
## Conclusion
This assignment helped me feel more confident writing Python functions and working with real data. Part 2 showed me how visualisations can reveal patterns and how statistical tests can support those findings. The biggest thing I learned was that testing code carefully really matters, especially when the data is messy.