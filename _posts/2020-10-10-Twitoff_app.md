---
layout: post
title: Twitoff - A Tweet Predictor
featured-img: TwitOff_logo
categories: [Application, Social Media, Predictor, Prediction, Data Engineering]
---	
## Twitoff: A Tweet Predictor! A Web Application!

This project was a website that we created (code wise) over a 2 week period. I was in unit 3 sprint 3 at Lambda School when we worked on this. We worked on it as a class and added our own individual code in order to personalize it. Everyone create their own website and deployed it to Heruko. 

<div align="center">
  <img src="https://joannemiddour.com/assets/img/posts/Twit-off_screenshot.jpg">  
  <em>This is the home page of my website application</em>
</div><br>

### Navigating my Web Application:

Once you click the [link](https://twit-off-jmiddour.herokuapp.com/) to go to my website, you will see the above image. Navigating this site is fairly easy. Depending on the size of your browser you will see either a "Update Tweets" button in the top right or "Menu", which you can click on and you will see the "Update Tweets" button. Clicking on the "Update Tweets" button will update all tweets already in my database to the most recent tweets that person has made since the last time the database was updated. That will take you to another page that looks just like the home page with one exception, where it says "Welcome to Twitoff" changes to "Updated Tweets". 

On the rightside of the home page is the listing of all the twitter handles that are already in my database. You can also add a user to my database if they don't already exsist. If you click on the twitter handle or put in someone that is already in my database and click add, it will take you to a page where you can see all the tweets in my database for that person. The only Tweets that will get added to my database are Tweets that were original tweeted by that user only. This means there will not be any retweets or tweets made by others about that person. Can just click on my Twitoff logo to return to the home page from here.

On to the fun part... On the left you can select 2 users that are in my database already. Then add some text and click the "Compare Users" button to find out which of the users are more likly to tweet the text you supplied. You will then see your prediction populate below the "Compare Users" button.

### The Process:

I used Flask and Flask-SQLAlchemy to build this web application and the database. Used the Tweepy API (Twitter's API) to access the realtime data directly from Twitter. We created our own functions to pull the data from Twitter and add it to our own database. We used the SpaCy small model to embed the input text. We used Logistic Regression for our predictive model. Then we were given a basic and very simple sample html code for the pages of our site but I did some research and self-taught myself ways to personalize what the site looked like and how it functioned. Then we learned how to deploy or application on Heruko so anyone can access it. You can view my code on my Github [here](https://github.com/jmmiddour/DSPT7-Twitoff) if you are interested.

### Conclusion:

This was the first time I have ever created a full website code with a search function, much less one that actually returns a prediction based on used inputs. I was so excited to be working on this project. The main thing that I enjoyed the most working on this was in just 2 weeks time I built something using code, from scratch, to create a product that anyone can access and use. I am excited to do more of these kind of application in the near future as side projects on things that interest me.

### Links:
  - Go to the website: [https://twit-off-jmiddour.herokuapp.com/](https://twit-off-jmiddour.herokuapp.com/)
  - Connect to my Github repository: [https://github.com/jmmiddour/DSPT7-Twitoff](https://github.com/jmmiddour/DSPT7-Twitoff)
