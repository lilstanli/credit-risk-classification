# credit-risk-classification


# REPORT

## BACKGROUND

The purpose of the analysis is to deduce a loan risk model to be used to evaluate loan repayment health of prospective borrowers based on the various existing features of past lending data of a p2p lending services company.

The data frame column “loan_status” was used as the target variable as it is the only true measure of the potential outcome while the rest of the columns on the other hand, was used as the features for the model. As can be seen from the analysis, there are more healthy loan statuses (75036) than the unhealthy or high-risk loan statuses (2500).

## LOGISTIC REGRESSION MODEL WITH THE ORIGINAL DATA

The data was run through a regression model and a prediction was generated using all the relevant features. Using the predicted data, the balanced accuracy score was calculated whiles the confusion matrix was generated for the model. Finally, with the original test values and predicted test values, a classification report was generated depicting the potential performance of the model.

- There was a near perfect overall accuracy of 99% with a 100% heathy loan precision and an 85% precision regarding high-risk loans.

## LOGISTIC REGRESSION MODEL WITH RESAMPLED TRAINING DATA

To Fix the skew or imbalance of the target y-values, the data had to be resampled. RandomOverSampler was used to resample the training data to obtain balanced training values of “56277” in the case of both healthy and high-risk loans. The data was run through a regression model and a prediction was generated using all the relevant features. Using the predicted data, the balanced accuracy score was calculated whiles the confusion matrix was generated for the model.

- There was 100% overall accuracy this time, while precision and f1-scores for healthy loans stayed at 100%.

- On the other hand, high-risk loan recall and f1-scores went up with recall having gone up 99%. High-risk loan precision however went down slightly all due to resampling.

## SUMMARY

Resampling the training data is the best approach as it removes biases allowing for a 1:1 ratio distribution. As the original test data leans heavily towards healthy loans (75036) versus high-risk (2500), the model will get most of its learnings from the majority class (healthy loans) which will make the result highly unreliable. After oversampling and receiving a 99% recall rate (an increase of 9% from 91%, which is not very bad at first glance), the results can be more reliable. As this is a financial related analysis, it is good to always have a more unbiased test data for an unbiased outcome.