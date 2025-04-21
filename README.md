# Project Title
Machine learning model to assist in the classification of claims for user submissions.

# Project Overview
* **The TikTok data team seeks to develop a machine learning model to assist in the classification of 
claims for user submissions. Earlier, the data team observed that if a user is verified, they are 
much more likely to post opinions. Since the end goal is to classify claims and opinions, it’s 
important to build a model that shows how to predict the behavior of the account type (verified) 
that tend to post more opinions. So, in this part of the project, the data team built a logistic 
regression model that predicts verified_status.**
* **After reviewing the provided dataset, the variable  
claim_status seemed particularly useful, given the client’s 
proposed project. The following screenshots show 
important points of analysis required to understand the 
claim_status variable**
* **The logistic regression model achieved a 
precision of 69% and a recall of 66% (weighted 
averages). This model achieved an f1 accuracy 
of 66%. These model results inform key insights 
on video features, discussed in “key insights.**
* **Based on the estimated model coefficients 
from the logistic regression, longer videos tend 
to be associated with higher odds of the user 
being verified.
 Other video features have small estimated 
coefficients in the model, so their association 
with verified status seems to be small. As a 
result, other video features besides video 
length do not seem to be associated with 
verified status.**

# Data Understanding
* **The purpose of the 
exploratory data analysis was to 
understand the impact that videos 
have on TikTok users.**
* ** `Null values`
 Over 200 null values were found in 7 different 
columns. As a result, future modeling should consider 
the null values to avoid making insights that would 
assume complete data. Further analysis is necessary 
to investigate the reason for these null values, and their impact on future statistical analysis or model 
building.

`Skewed data distribution`
 Video view and like counts are all 
concentrated on low end of 1,000 for 
opinions. Therefore, the data distribution is 
right-skewed, which will inform the models 
and model types that will be built.
 their impact on future statistical analysis or model 
building**
* **There is a near equal balance of opinions versus 
claims. With this understanding, we can 
proceed with our future analysis knowing that 
there is a fairly balanced amount of claims and 
opinions for the videos included within this 
dataset.**

* **With the key variables identified and the initial 
investigation of the claims classification 
dataset, the process of exploratory data 
analysis can begin**

# Model Evaluation
* Both model architectures—random forest (RF) and 
XGBoost—performed exceptionally well. The RF 
model had a better recall score (0.995) and was 
selected as champion.
* Performance on the test holdout data yielded near 
perfect scores, with only five misclassified samples 
out of 3,817.
* Subsequent analysis indicated that, as expected, the 
primary predictors were all related to video 
engagement levels, with video view count, like count, 
share count, and download count accounting for 
nearly all predictive signal in the data. With these 
results, we can conclude that videos with higher user 
engagement levels were much more likely to be claims. 
In fact, no opinion video had more than 10,000 views.

# Conclusion
1. **Would you recommend using this model? Why or why not?**
>Yes, one can recommend this model because it performed well on both the validation and test holdout data. Furthermore, both precision and F<sub>1</sub> scores were consistently high. The model very successfully classified claims and opinions.

2. **What was your model doing? Can you explain how it was making predictions?**
>The model's most predictive features were all related to the user engagement levels associated with each video. It was classifying videos based on how many views, likes, shares, and downloads they received.

3. **Are there new features that you can engineer that might improve model performance?**
>Because the model currently performs nearly perfectly, there is no need to engineer any new features.

4. **What features would you want to have that would likely improve the performance of your model?**
>The current version of the model does not need any new features. However, it would be helpful to have the number of times the video was reported. It would also be useful to have the total number of user reports for all videos posted by each author.

Remember, sometimes your data simply will not be predictive of your chosen target. This is common. Machine learning is a powerful tool, but it is not magic. If your data does not contain predictive signal, even the most complex algorithm will not be able to deliver consistent and accurate predictions. Do not be afraid to draw this conclusion.


