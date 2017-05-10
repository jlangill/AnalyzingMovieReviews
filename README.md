# AnalyzingMovieReviews
Challenge: Analyzing Movie Reviews
In this project, I'll be working with Jupyter notebook, and analyzing data on movie review scores.

The dataset is stored in the fandango_score_comparison.csv file. It contains information on how major movie review services rated movies. The data originally came from FiveThirtyEight.

Instructions
Read fandango_score_comparison.csv into a Dataframe named movies.
Display the movies DataFrame by just typing the variable name and running the code cell.
If you're unfamiliar with RottenTomatoes, Metacritic, IMDB, or Fandango, visit the websites to get a better handle on their review methodology.

Enable plotting in Jupyter notebook with import matplotlib.pyplot as plt and run the following magic %matplotlib inline.
Create a histogram of the Metacritic_norm_round column.
Create a histogram of the Fandango_Stars column.
Look critically at both histograms, and write up any differences you see in a markdown cell.

Calculate the mean of both Fandango_Stars and Metacritic_norm_round.
Calculate the median of both Fandango_Stars and Metacritic_norm_round.
Calculate the standard deviation of both Fandango_Stars and Metacritic_norm_round. You can use the numpy.std method to find this.
Print out all the values and look over them.
Look at the review methodologies for Metacritic and Fandango. You can find the metholodogies on their websites, or by using Google. Do you see any major differences? Write them up in a markdown cell.
Write up the differences in numbers in a markdown cell, including the following:
Why would the median for Metacritic_norm_round be lower than the mean, but the median for Fandango_Stars is higher than the mean? Recall that the mean is usually larger than the median when there are a few large values in the data, and lower when there are a few small values.
Why would the standard deviation for Fandango_Stars be much lower than the standard deviation for Metacritic_norm_round?
Why would the mean for Fandango_Stars be much higher than the mean for Metacritic_norm_round.

Make a scatterplot that compares the Fandango_Stars column to the Metacritic_norm_round column.
Several movies appear to have low ratings in Metacritic and high ratings in Fandango, or vice versa. We can explore this further by finding the differences between the columns.
Subtract the Fandango_Stars column from the Metacritic_norm_round column, and assign to a new column, fm_diff, in movies.
Assign the absolute value of fm_diff to fm_diff. This will ensure that we don't only look at cases where Metacritic_norm_round is greater than Fandango_Stars.
You can calculate absolute values with the absolute function in NumPy.
Sort movies based on the fm_diff column, in descending order.
Print out the top 5 movies with the biggest differences between Fandango_Stars and Metacritic_norm_round.

Calculate the r-value measuring the correlation between Fandango_Stars and Metacritic_norm_round using the scipy.stats.pearsonr function.
The correlation is actually fairly low. Write up a markdown cell that discusses what this might mean.
Use the scipy.stats.linregress function create a linear regression with Metacritic_norm_round as the x-values and Fandango_Stars as the y-values.
Predict what a movie that got a 3.0 in Metacritic would get on Fandango using the formula pred_3 = 3 * slope + intercept.

Predict what a movie that got a 1.0 in Metacritic would get on Fandango using the line from the last screen.
Predict what a movie that got a 5.0 in Metacritic would get on Fandango using the line from the last screen.
Make a scatter plot using the scatter function in matplotlib.pyplot.
On top of the scatter plot, use the plot function in matplotlib.pyplot to plot a line using the predicted values for 1.0 and 5.0.
Setup the x values as the list [1.0, 5.0].
The y values should be a list with the corresponding predictions.
Pass in both x and y to plot to create a line.
Set the x-limits of the plot to 1 and 5 using the pyplot.xlim() method.
Show the plot.

