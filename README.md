# Welcome!
Here you will find a wonderful and brilliant weather website! After typing a city, an image and an emoji will be displayed based on the current weather!
Before I explain how this website works, I must tell you the trials and tribulations I faced to get here...

*A GOOD WEBSITE DOESN'T COME EASILY!*

## Adding the Cats
Talk about simple problems. I was using a JS cheat sheet website to help me add the images to my website. Not terribly hard after figuring out that my images must be called before calling the script in my index.html file (and also removing an incorrectly called source...) 

**However**, the images still could not be displayed. So, what was the problem you might be wondering? **I LABELED THE IMAGE FILES WRONG IN THE SCRIPT.JS FILE! THAT WAS IT!** Considering I was the one who downloaded and renamed the files, you think that would be the one thing I do right. 

## Updating the Emojis
What should've been a very easy update to the code instead had me fighting for my life, hunched over my laptop. You see, when the temperature is below 40, the emoji will be "❄️". When the temperature is above 60, the emoji will be "🌤️". However, when the temperature is between 40 and 60, the emoji displayed will be "☁️". For some reason, when the temperature is between 40 and 60, both emojis (🌤️☁️) are shown! Here was my original code: 
```
infoField.innerHTML = "The weather in " + locationField.value + " is " + response.days[0].temp
    if (response.days[0].temp < 60 && response.days[0].temp > 40) {
      infoField.innerHTML += " ☁️"
      imgElement.src = "images/catcloud.jpg";
    }
    if (response.days[0].temp < 40) {
      infoField.innerHTML += " ❄️"
      imgElement.src = "images/snow.jpg";
    }
    else {
      infoField.innerHTML += " 🌤️"
      imgElement.src = "images/suncat.jpg";
    }
```
Seemed like it would be completely right, right? **WRONG**! 
Here is the *correct* code. 
```
if (response.days[0].temp < 40) {
  infoField.innerHTML += " ❄️";
  imgElement.src = "images/snow.jpg";
}
else if (response.days[0].temp < 60) {
  infoField.innerHTML += " ☁️";
  imgElement.src = "images/catcloud.jpg";
}
else {
  infoField.innerHTML += " 🌤️";
  imgElement.src = "images/suncat.jpg";
}
```
I don't want to talk about how long it took to figure that out. Definitely did a *lot* of Google searching... It was such a simple fix, I just needed the **else if** statement. 

## Designing the Design
After fixing the major errors in my code, I just messed around getting things to look a little nicer, a little more Relena.

<img width="200" height="180" alt="Screenshot 2026-03-06 at 12 21 34 PM" src="https://github.com/user-attachments/assets/edb85a27-2f83-4c67-a39c-361c761d1444"/>
cat 

This website was made using Visual Crossing Weather API from RapidAPI. 






