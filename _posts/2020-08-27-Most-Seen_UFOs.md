---
layout: post
title: What Will be the Most Seen Shape of UFOs in the Future?
featured-img: UFO
categories: Research-Project, UFO, Space
---	
### Based on real reported UFO sightings  


![Image of UFO](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/UFO.jpg)  
*Source for image: [Vecteezy](https://www.vecteezy.com/vector-art/1215226-ufo-realistic-galaxy-design)*


---
## Reported UFO Sightings through the Years  
My research started with a data set I found on [Kaggle](https://www.kaggle.com/NUFORC/ufo-sightings?select=scrubbed.csv) with 80,332 observations (rows/sightings) and 11 features (columns). This is data that was collected by the [National UFO Reporting Center (NUFORC)](http://www.nuforc.org/). 
The original data contained reported sightings for the last century dating back to 1906 up to 2014. However, after examining the data, I found that before 1994 there is not a significant amount of data (as you can see in the graph above). Therefore, the data I will base my predictions on will be from 1994 to 2014.



|![Yearly Reported Sightings 1906-2014](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Year_of_reported_sightings_chart.png)|![Yearly Reported Sightings 1994-2014](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Year_of_reported_sightings_1994-2014.png)|
| --- | --- |
| _This graph shows the frequency of the number of reported sightings based on the year of the sighting. This is all of the original years from the data set._ | _This graph shows the frequency of sightings after removing the years._ |



As you can also see from the top graph to the left, there were not many “reported” ufo sightings prior to around 1954. There could be many reasons for this. Maybe there just were not that many sightings back then. Could it be that people were just embarrassed to say anything out of fear of being ridiculed or being accused of being “crazy”? Maybe they just did not know how to report a sighting. Without more real data, that may be something we will never know for sure but, if I had to guess, I would say, more than likely, it was the fear that kept people from reporting sightings.

There are several reasons I can think of that the reported sightings started spiking in the mid-1990s. One could be that it was more widely excepted by the populous. It could have also been that cameras were more readily available to take photographic proof. Maybe it was that the internet started to become more of a staple in a lot of homes, therefore, more access to information that was not available prior. Also, easier access to being able to report the sightings. People tend to be more comfortable admitting to something they saw if they know they are not the only ones who have seen it.

---
## My Target Feature and why I used it:  
My target feature is a feature I created with data from the shape column. The original shape feature was divided into 30 (including the N/A values) different shapes. I created a feature for shape classes to reduce the dimensionality of the feature target. The classes I created are listed below, along with the original shapes that went into these classes:



<script src="https://gist.github.com/jmmiddour/bf186705cd5db63838d9640c6c7c9ea1.js"></script>  
_Here is a table of the Shape Classes I assigned and what the original shapes were for each class._



I decided to use the shape class because of my own curiosity based on how the shapes have changed over the years. You have the typical circular / saucer shape that was mostly what people would say they saw for a while. Then you started to hear of different types of lights, triangular-shaped, multiples, formations, cigar-shaped, etc. I wanted to see if it was possible, based on real historical data, to predict what the most seen shape will be in the near future just by adjusting certain features, such as time, hour, day of the week, location, etc..

---
## Some of the Processing I did:  
The very first thing I did was explore my data using the [pandas profile report](https://joannemiddour.com/UFO_pd_profile_report.html).  
After exploring my data I realized, even though this was a dataset that was already scrapped, there was a lot of cleaning I needed to do prior to being able to do a 3-way split on my data. One of the first things I needed to do was to change the DateTime feature to DateTime format so that I could then split up the date into the year, month, day of the week, and hour.  

Next, it was time to look at the null values. I temporarily replaced all nan values with 0 to make it easier to do the rest of the cleaning I needed to do. I also had a problem value in the latitude feature that was a typo that I needed to fix. I fixed capitalization problems as well.  

This dataset had locations all over the world. While exploring the data, I noticed that the majority of reported sightings were in North America. So I decided to drop all rows that were not in the United States, Canada, Puerto Rico, Alaska, or Hawaii. There were also a lot of empty values in the country column that I needed to fill in based on the city and state columns. This did take some research on my part because I had to verify the locations to make sure I was inputting the proper location.  

Next, I tried my hand at doing some NPL (Natural Language Processing). In a nutshell, NPL breaks down a column that has several words in it and turns each word into its own column with a count of how many times that word was used within that text. This was a big undertaking for me as this is not something we have learned about yet. However, I felt this might benefit my predictive power by breaking down the values in the comments feature.  

Unfortunately, NPL was not as helpful as I was hoping it would be and would have provided some data leakage. I did benefit personally though from all the time it took to do this because it was enjoyable to learn how to do it. After doing some more basic cleaning, I was then able to do my 3-way split on the data set to get my training, validation, and testing sets. Then I was able to create my (X) feature matrices and my (y) target vectors.  

---
## A Visualization to Show Some of the Data Used for Predicting:  



![](https://github.com/jmmiddour/jmmiddour.github.io/blob/master/assets/img/posts/Shape_class_by_year.png)  
_This box plot represents if a type of movement was mentioned in the comments for the reported sightings.  
I grouped them by the year the sighting occurred and what shape class was reported._



---
## What are my Baseline Scores?  
I calculated my Baseline score based on the percentage of the majority class frequency in my target feature. The **baseline score** I get is only **31.90%**. This is probably because I have 6 different classes in my target feature. This is to be expected because this was not a binary class.



![](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Shape_class_by_country.png)  
_This count plot shows the distribution of the shape classes based on my training data._



Then I checked what my **accuracy score** would be based on guessing the majority class for all predictions on my test dataset. I got the same at **31.90%** and this was of no surprise to me since this is the average of the majority class.

---
## Some Logistic Regression:  
Logistic Regression has a deceiving name because it is actually for doing classification problems. It measures the relationship between dependant and independent variables by estimating the probabilities of a prediction. It is best used with binary variables but can be used with more complex multi-class classification variables.  

I used a Logistic Regression model and tuned the hyperparameters. The best result that I was able to obtain was a **Train Accuracy Score** of **31.78%**, which is actually lower than my baseline. My **Validate Accuracy Score** was **31.59%**, which is only slightly better than my baseline. This means there is a very small difference between the Train and Validate Score of only 0.19%. I don’t think I would have been able to get this model to fit any better without overfitting it.

Then I checked my accuracy score based on my test set once I decided on my final parameters. I actually got a better score than my validation set. My **Test Accuracy Score** is **31.87%**, which is slightly lower than my baseline.



![](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Coefficients.png)  
_This shows my coefficient values for each of my features in relation to the Shape Class._



I also plotted my coefficient values for all of my features based on my logistic regression model. The higher the coefficient value is, the better relationship that feature has with the target feature. If it is a positive number that just means that it is positively correlated and if the value is negative, it still is related to the target but that means it has a negative correlation. The closer the coefficient value is to 0, the less of a relationship it has to the target.



![](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Confusion_matrix_log_regression.png)  
_This Confusion Matrix is based on my Logistic Regression Model._



The confusion matrix above shows how my predictions relate to the actual data in the test data set. On the “y” (horizontal) axis is all the actual values (True Label) from my test data set. Then on the “x” (vertical) axis is all of the predictions (Predicted Label) that my model made based on the information in my training data set.



![](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Classification_report.png)  
_A heatmap to display the values from my classification report based on logistic regression._



---
## Accuracy Score with Random Forest Modeling:  
A Random Forest model is a tree-based learning algorithm. It uses a collection of another tree-based algorithm called decision tree for classification and regression problems. I used the Random Forest Classifier since my problem is a multi-class classification problem.

I created a random forest model and did some hyperparameter tuning. After several attempts to get a better model, the results of the best model I got were: **Train Accuracy Score** of **0.3864095825331042 (38.64%)** and **Validate Accuracy Score** of **0.3686444961083594 (36.86%)**. This gives me a **difference** of **only 0.01776508642474478 (1.78%)** between the Train and Validate Scores. I got a lot closer with the difference between scores using the Logistic Regression Model but my accuracy scores were not as high.

Then after I was happy with the hyperparameters I choose. I got my **Test Accuracy Score** which was **0.3624161073825503 (36.24%)**. That is slightly lower than my validation score. However, this score is much better than my logistic regression model gave me. So we are at least heading in the right direction. My predictive power is improving.



![](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Feature_importance.png)  
_This horizontal bar chart shows how important my features are in relation to predicting my target value._  



The feature importance for a random forest model helps to explain what features contribute most to the decision making of the algorithm or predictive power in the model. This helps you to better decide on what features to include in your model and what features you can drop because they do not really help the model to predict the target value.

---
## Permutation Feature Importances:  



![](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Permutation_importance.jpeg)  
_Permutation Feature Importances_



I used the same Random Forest Model to get my permutation feature importances. This will help me to determine the importance of my features to help increase my predictive power. The darker the green is, the more important a feature is in relation to predicting my target value.

---
## Let’s take a look at some PDP’s (Partial Dependency Plot):  
Since the hour and year were at the top of my permutation feature importances, I decided that I wanted to look at a partial dependency plot to see the relationship between the two in comparison to my target classes.


![](https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/PDP_plots.png)  


---
## Conclusion:  
Although I did not get high accuracy scores based on the model I chose to work with, I did find that the Random Forest model was the best fit for making my predictions. I was actually very surprised that certain features did not hold more weight when predicting the shape of a UFO. I really did enjoy working with this dataset though and I will definitely be working on some other projects using it. To me, it was very interesting to find out that the most reported shape seen was some kind of light. I was under the impression, prior to doing this project, that the most seen shape in North American countries was of the circular type. Although it did rank as a close second.

---
## Resources:  
- Where I found my original dataset: [Kaggle](https://www.kaggle.com/NUFORC/ufo-sightings?select=scrubbed.csv)  
- Where the data was collected from for the dataset: [National UFO Reporting Center (NUFORC)](http://www.nuforc.org/).  
- If you would like to see the stats for the original dataset I started with, you can look at my [pandas profile report](https://joannemiddour.com/UFO_pd_profile_report.html).  
- You can see my notebook on [GitHub](https://github.com/jmmiddour/Projects/blob/master/UFOs/UFO_Unit_2_Project.ipynb)  
- You can view my [Medium Blog Post](https://medium.com/@magical_satin_seal_239/what-will-be-the-most-seen-shape-of-ufos-in-the-future-fa5a4f2b5d0e)
