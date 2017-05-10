# AnalyzingMovieReviews
Challenge: Analyzing Movie Reviews
In this project, I'll be working with Jupyter notebook, and analyzing data on movie review scores.

The dataset is stored in the fandango_score_comparison.csv file. It contains information on how major movie review services rated movies. The data originally came from FiveThirtyEight.

Here are the first few rows of the data, in CSV format:

FILM	RottenTomatoes	Metacritic	IMDB	Fandango_Stars	RT_norm	RT_user_norm	Fandango_votes
0	Avengers: Age of Ultron (2015)	74	86	7.1	7.8	4.5	3.70	271107
1	Cinderella (2015)	85	80	7.5	7.1	4.5	4.25	65709
2	Ant-Man (2015)	80	90	8.1	7.8	4.5	4.00	103660
3	Do You Believe? (2015)	18	84	4.7	5.4	4.5	0.90	3136
4	Hot Tub Time Machine 2 (2015)	14	28	3.4	5.1	3.0	0.70	19560
Each row represents a single movie. Each column contains information about how the online moview review services RottenTomatoes, Metacritic, IMDB, and Fandango rated the movie. The dataset was put together to help detect bias in the movie review sites. Each of these sites has 2 types of score -- User scores, which aggregate user reviews, and Critic score, which aggregate professional critical reviews of the movie. Each service puts their ratings on a different scale:

RottenTomatoes - 0-100, in increments of 1.
Metacritic - 0-100, in increments of 1.
IMDB - 0-10, in increments of .1.
Fandango - 0-5, in increments of .5.
Typically, the primary score shown by the sites will be the Critic score. Here are descriptions of some of the relevant columns in the dataset:

FILM -- the name of the movie.
RottenTomatoes -- the RottenTomatoes (RT) critic score.
RottenTomatoes_User -- the RT user score.
Metacritic -- the Metacritic critic score.
Metacritic_User -- the Metacritic user score.
IMDB -- the IMDB score given to the movie.
Fandango_Stars -- the number of stars Fandango gave the movie.
To make it easier to compare scores across services, the columns were normalized so their scale and rounding matched the Fandango ratings. Any column with the suffix _norm is the corresponding column changed to a 0-5 scale. For example, RT_norm takes the RottenTomatoes column and turns it into a 0-5 scale from a 0-100 scale. Any column with the suffix _round is the rounded version of another column. For example, RT_user_norm_round rounds the RT_user_norm column to the nearest .5.

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

