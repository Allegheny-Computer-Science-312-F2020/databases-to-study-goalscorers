This file is to contain the actual report for your work. Note, you can copy and edit this code to add graphs to your document. Note, your images will have to be stored in the directory, `images/`. Please see the assignment sheet for details.
![Screenshot](images/blueCat.png)


#### Name:
Declan Casey

#### Date:
12/11/2020

### Title: Using Databases to Study The World's Top Goalscorers

#### Data set
The five datasets I used were found @ https://footystats.org/download-stats-csv#. The data isn't free, but I had already subscribed for a personal project I was doing so it was no issue.

#### Project Overview
This research project uses databases to study the soccer world's top goalscorers.  A few questions that I specifically wanted to ask and answer are:

- What advanced metrics are most common in elite goal scorers?
- What advanced metrics that are not direct goal contributions (goals, assists, major stats such as these) contribute to an elite goal socers success?
- What are some stand-out metrics that are unique to individual goal scorers?
- Are there specific offensive stats that most elite goal scorers tend to not be elite in? For example, maybe the data shows most of the top scorers score less in away games or vice versa.
- Do the amount of goals their team conceded in games they played in seem to correlate to how many they score? Does a team's performance affect their individual performance?

##### Motivation
In order to be enthusiastic about the actualy results of the research I performed, I tried to tie pick an field that was genuinely interesting to me. I am a big sports fan, and the world's most elite soccer leagues, commonly referred to as the "Top 5", got underway just under 2 months ago. The top 5 leagues are the Premier League in England, Ligue 1 in France, the Bundesliga in Germany, Serie A in Italy, and La Liga in Spain. These teams have dominated european soccer for decades and contain the vast majority of elite players in the entire world. Studying these leagues will give me better insight about the best goalscorers more than any others. There are a few other popular leagues, but none that contain the amount of elite players as the Top 5.

One aspect fascinating aspect of modern sports is that they are constantly evolving, whether it's because of rule changes, changes in playing styles over time, or because of players who are so good that they change the way the game is played. Particularly in soccer, there haven't been many rule changes that have drastically affected the way the game is played, but there have been several generational players who have fundamentally changed the way people view the sport, such as Cristiano Ronaldo and Lionel Messi, as well as many changes in playing styles. There are so many different kinds of playing styles that trying to study them all would be too dificult and probably wouldn't come to a specific learning outcome because of the sheer mass of data.

For this project I decided to study attackers only, as there are far more valuable attacking stats than there are defensive stats. Also, judging a defender based off of their individual stats isn't fair to them, as there are no direct defensive stats that clearly show their output on the field. For example, attackers can score a goal or an assist and the more they have of each the more effective they are. Defenders have stats such as tackles and interceptions, but they don't directly show just how effective they are. Also, attacking stats are much more fun!

##### Background Information
It is important to note that although data and statistics are very important in deciding how effective a player is, there are many traits and skills that we have to found a way to quantify statistically. Reasearchers out of Spain noted one skillset that is hard to quantify is a player's [motor skill](https://www.frontiersin.org/articles/10.3389/fpsyg.2017.00741/full) and they actually began to develop and improve upon previous methods of analyzing motor skills. They developed 50 sub-categories ubderneath the motor skills main category and used "T-pattern detection and polar coordinate analysis" to make connections and associations between these patterns. Polar coordinate analysis provides a "vector map of interrelated behaviors obtained from prospective and retrospective sequential analysis," and T-Pattern analysis "temporal structures of complex behavioral sequences" using smaller, previous events within specified observation times. These researchers have shown that in order to perform quantifiable research and hard-to-quantify categories is very tedious.




##### References
- Castañer, Barreira, Camerino1*, Anguera, Fernandes, and Raúl Hileno. 2017, "Mastery in Goal Scoring, T-Pattern Detection, and Polar Coordinate Analysis of Motor Skills Used by Lionel Messi and Cristiano Ronaldo," Frontiers of Psychology



##### Building the Database System
There were several important steps in building the database system. The first step was acquiring good, reliable data for each of the top 5 leagues, which was much harder than originally expected. Most of the data that I found did not contain enough advanced statistics, which are a combination of several data points, rather than just a a one-dimensional stat like goals or asists. For example expected goals (xg) is the measure of the quality of a shot based on several variables such as assist type, shot angle, distance from goal, whether it was a header, and whether it was a big chance. There are many important advanced stats in the data that I did end up finding, but this data was not free of charge. Luckily I had already subscribed to the website that held the data due to previous personal research. The dataset I found has at least 1,000 entries per league, which was more than enough and contained up over 40 different columns of data.

The next step was cleaning and filtering the data before building a database file. I deleted about 15-20 attributes that I was not planning on examining, such as defensive stats. There were other categories that I wasn't planning on researching at first, but decided to leave them in as they could have been of later use. The cleaning process was a bit tedious as I had 5 datasets that were quite large, but since they all came from the same source they were all formatted uniformly, which sped up the process.

I decided to use SQLite3 as it was the language and database system that I understood the most, and given that it relies almost entirely on tables, it mimics a top scorers board in the real world. The first table below is what the actual top scorers table looks like, and the second one is how my data is formatted. Although they are not the exact same, they do have similarities.

![alt text](realTable.png "Real Premier League Top Scorers List")

![alt text](eplDataTable.png "What My Data Looks Like")

Another reason for using SQL was the simplicity of querying and database building using a txt file called `soccerStats_build.txt`. The only code of importance outside of the import statements below is the command to run the the builder file, `/* cat soccerStats_build.txt | sqlite3 soccerStatsDB.sqlite3 */`, and also the separator, `.separator ","` which will  separate the data being imported with a comma, `,`. This is because the database will be reading in CSV files where the values are separated by commas rather than tabs, indents, etc.

The next step was figuring out how exactly to read the data in. Since my data came with headers for each column, I decided not to mess with the format too much, and not build individual schemas for each table in the builder file. It was much easier to just import the entire csv files themselves as their own table:

```
.import data/Budesliga-player-stats-1920-final.csv Bundesliga
.import data/EPL-player-stats-1920-final.csv EPL
.import data/LaLiga-player-stats-1920-final.csv LaLiga
.import data/Ligue1-player-stats-1920-final.csv Ligue1
.import data/SerieA-player-stats-1920-final.csv SerieA
```

###### Tables & Schema
The database building process went very smoothly and all of my tables and schemas were set up correctly and contained all of the correct information. Again, there are five tables in my database one for each of the top 5 leagues. They all contain the same attributes but different amounts of data given that each league has a different amount of players. This means they all have the same schema. Here is an example of the schema of one of my tables, the English Premier League.

![alt text](eplSchema.png "EPL Schema")



#### First Research Question and Background
##### Queries
##### Results
##### Graphics

#### Second Research Question and Background
##### Queries
##### Results
##### Graphics

#### Third Research Question and Background
##### Queries
##### Results
##### Graphics

#### Fourth Research Question and Background
##### Queries
##### Results
##### Graphics

#### Fifth Research Question and Background
##### Queries
##### Results
##### Graphics



##### Conclusion





(Did you remember to add your name to the top?)
