__Partners: Corinne & Myitzu__

__Major decisions__
We chose the city of Amsterdam as it had many observations (2,058). We added a column to the dataframe called 'highly_rated' which was simply the 'rating' column when hotels were rated 4 or higher. We then made the 'highly_rated' variable a dummy variable (1 if highly_rated (rating of 4 or larger), 0 if not (rating less than 4)).

__LPM:__ We performed a linear probability model regression (LPM) in order to see how unit changes in *distance* and *stars* would affect the probability of the dependent variable being 1 (a hotel being highly rated). 
- (constant coefficient) the constant coefficient doesn't seem to have an interpretable meaning here. It is also negative (despite the depedent variable ranging from 0-1 (limitations of LPM)).
- (distance coefficient) for one unit increase in distance, hotels are more likely to be highly rated by 2.7 percentage points. p value is 0 (or near 0) meaning distance is statistically significant (most likely a relationship between distance and probability of a hotel being highly_rated (having more than 4 stars)).
- (stars coefficient) for one unit increase in stars, hotels are more likely to be highly raetd by 28.7 percentage points. p value is 0 (or near 0) meaning stars is statistically significant (most likely a relationship between stars and probability of a hotel being highly_rated (having more than 4 stars)).

__Logit:__  We produced a table with logit regression results, however for logit regressions, the coefficients are hard to interpret, so we must use marginal effects in order to get coefficients similarly interpretable to a LPM. We then create a logit marginal effects table. 
Results:
- (distance coefficient) for one unit increase in distance, hotels are more likely to be highly rated by 2.27 percentage points. p value is 0 (or near 0) meaning distance is statistically significant (most likely a relationship between distance and probability of a hotel being highly_rated (having more than 4 stars)).
- (stars coefficient) for one unit increase in stars, hotels are more likely to be highly raetd by 27.42 percentage points. p value is 0 (or near 0) meaning stars is statistically significant (most likely a relationship between stars and probability of a hotel being highly_rated (having more than 4 stars)).

__Probit:__ We produced a table with probit regression results, however similarly to logit, the coefficients are hard to interpret. Therefore, we created a probit marginal effects table.
Results:
- (distance coefficient) for one unit increase in distance, hotels are more likely to be highly rated by 2.11 percentage points. p value is 0 (or near 0) meaning distance is statistically significant (most likely a relationship between distance and probability of a hotel being highly_rated (having more than 4 stars)).
- (stars coefficient) for one unit increase in stars, hotels are more likely to be highly raetd by 27.42 percentage points. p value is 0 (or near 0) meaning stars is statistically significant (most likely a relationship between stars and probability of a hotel being highly_rated (having more than 4 stars)).

__Predicted Probabilities:__
The predicted probabilities for all three models (LPM, Logit, and Probit) were all similarly in the 0.5 region indicating that ambiguity in predicting the probability of hotels being highly rated.
However, looking at the fit of the predicted probabilities (using R-squared and Brier-score), the Logit model proved to provide the best fit for the predicted probability of hotels being highly_rated. (Probit model was almost exactly the same)

__Overall Summary:__
Distance from city center and Stars seem to both have a positive relationship with hotels being highly rated (would reject null hypothesis that they didn't have relationship). This was expected from stars, but not from distance. However, both variables are statistically significant and therefore we can assume the relatinship is meaningful. Lastly, the Logit Model proves to provide the best fit for understanding the marginal effects. 
