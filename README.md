# Metascore Prediction from Game Summaries.
## A Binary Classification with NLP
### Nikesh Suthar - BrainStation 2020 Dipolma Graduate 
___
## Project Overview

As an avid gamer, I've always had trouble finding new games to play and usually go back to the classics. What I wanted to acheive find a way to choose a new game without knowing the title, or what platforms its played on or even who created the game. I wanted to find a way to play new games without bias so I decided that I would want to play games which were higly rated. The only rating system in place for games would be metascore. Since metacritic is a highly known rating website, I chose their rating system because I believe it is the only relible rating system for games.

The model was trained on the games metascore as the target and the summary as the values. This allowed me to take a game summary and predict a score of 0 (low rated) or 1 (high rated). I chose to do this because I want to see if my model would be accurate enough to be able to predict if a new game will be highly rated before it is reviewed. 
This would make review games slightly easier since if it were a highly rated game more people would play newer games rather than sticking to the same game. 

## Data Gathering

All the data was gathered from MetaCritics website, I looked into all the games released on 21 differnet platforms, with a metascore rating. Many of the newer games do not have a metascore rating so they would have skewed the data which would have cause the data to have more 0 values than 1s. From the web scraping data included; game title, genres, metascorea and summaries. I chose not to include the release date since majority of the game where released between 2000-2010 which again would have had skewed the machine learning process favoring these years. 

## EDA and Trends

Some interseting trends I found throughout the process of my data set were:
* Metascore Frequency 
![Image](Images\Histo.png)
This trend shows that the majority of games rating is between 75-85 from all platforms.
   
* Mean Metascore of each platform
![Image](Images\MPM.png)
This trend shows the mean metascore for each platform. Each platform averages around 60-75, just the number of games vary.

* Total Number of Games per Platform
![Image](Images\platform_counts.png)
This trend shows the total number of games per platform. As we can see in the graph above, PC has the most amount of games released followed by iOS.

* Weighted Words from TFIDF
![Image](Images\words.png)
The word game was the most highly rated word. Any combination of these top 50 words would make any game have a high rating. 

## Model

For my model I ended up using a LinearSVM model rather than a Logistic Regression model since SVM models tend to do much better with text data since helps to choose a good value from said margin, distance between the line and the support vectors, and then can classify the text as a whole. Also I chose LinearSVM since it was better at predicting highl rated games than lowly rated games.

## Future Works

I plan on turning this Binary classification into a multiclassification and seeing if the model can predict an actual rating between 0-100. I also want to be able to build a recommandation system off the text data enter to show games that are simialr to the summary in question. 
