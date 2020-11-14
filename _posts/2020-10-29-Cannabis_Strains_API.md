---
layout: post
title: Cannabis Strains API
featured-img: Cannabis_API_screenshot
categories: [Application, Medical, Predictor, Prediction, Data Engineering]
---
## Cannabis Strains API

This project was the first one where I worked with a team. The team consisted of 6 full stack web students and 3 Data Science students. I was in unit 3 at Lambda at the time of the creatation. Of the other Data Science students there was another unit 3 student and a unit 4 student. Being a unit 3 student we were tasked with creating the API to connect the the front end to the database and the predictive NLP model, which was created and trained by the unit 4 student. Then our API returned a json file for the web team to use based on the string(s) they sent to our API. 

<div align="center">
  <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Cannabis_API_screenshot.jpg">  
  <em>This is a screenshot of our API</em>
</div><br>

<details>
  <summary><strong>How to use our API</strong></summary><br>
  Once you click the <a href="https://strains-cannabis.herokuapp.com/">link</a> to go to our API, you will see the above image. At the top of the page, just below the image, is a link where you can <a href="https://strains-cannabis.herokuapp.com/redoc">view the docs</a> for our API. Our API is simple to navigate. 
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/PostRequest.jpg">  
    <em>Create a request for a prediction by clicking on the green <b>"POST"</b> button. </em>
  </div>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/TryIt-Post.jpg">  
    <em>Click on the <b>"Try it out"</b> button.</em>
  </div>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Execute-Post.jpg">  
      <em>Replace the string for ailment, flavor, and effects.<br>
      Ailment is the only required input and has a default value of "stress and insomnia", which you can change.<br>
      Then click on the <b>"Execute"</b> button</em>
  </div>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/ReponseBody.jpg">  
  </div>  
   <em><b> --> A.</b> Curl request<br>
       <b> --> B.</b> Request URL<br>
       <b> --> C.</b> Best matched strain<br>
       <b> --> D.</b> Next best strain match<br>
       <b> --> E.</b> Rest of the top 5 matches<br>
       <b> --> F.</b> Click to download the json file with the results</em>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Get.jpg">  
    <em>To get all of the strain data in our database, click the blue <b>"GET"</b> button</em>
  </div>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/TryIt-Get.jpg">  
    <em>Click the <b>"Try it out"</b> button</em>
  </div>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Execute-Get.jpg">  
    <em>Click the blue <b>"Execute"</b> button</em>
  </div>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/ReponseBody-Get.jpg"> 
  </div> 
  <em><b> --> A.</b> Curl request<br>
      <b> --> B.</b> Request URL<br>
      <b> --> C.</b> All the strains and information we have in the database.<br>
      <b> --> D.</b> Click to download all of the strains in our database as a json file.</em>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Inputs_schema.jpg">  
    <em>The inputs schema.</em>
  </div>
  <br>
    <hr>
  <br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/jmmiddour/jmmiddour.github.io/master/assets/img/posts/Strains_schema.jpg">
    <em>The strains schema.</em>
  </div>
  <br>
    <hr>
  <br>
</details>

## Links:
- The API the DS team created: [Cannabis Strains API](https://strains-cannabis.herokuapp.com/)  
- The [docs for our API](https://strains-cannabis.herokuapp.com/redoc).  
- The completed website created by the web team: [Med Cabinet](https://medcabinent.netlify.app/index.html)  
- You can see everyone that participated in this project: [About page](https://medcabinent.netlify.app/about.html)  
- Data Science team's completed code on [Github](https://github.com/Build-Week-Med-Cabinent-4/data-science)  
