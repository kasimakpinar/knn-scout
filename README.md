# KNN Scout

## Introduction

Recently, Real Madrid sold Cristiano Ronaldo to Juventus. Who should they sign for a replacement?

Well, data science shows that the best option is to buy **Harry Kane** from Tottenham. Also, Ciro Immobile could be usefull addition to the squad since data science shows that he has similar playing style. Surprisingly, it seems that non-famous 18 years old Newells Old Boys player Enzo Cabrera also has similar playing style with Cristiano Ronaldo. Good prospect for the future, maybe?

In this project, we will use machine learning to try to find football players who has similar playing style with a given base player.

Thanks to [whoscored.com](https://www.whoscored.com/), we have detailed statistics for players. This project is a good example of using KNN Algorithm.

## Table of Contents
[1. Data](1-data)
[2. Methods](2-methods)
[3. Results](3-results)
[4. Resources](4-resources)

## 1. Data
[whoscored.com](https://www.whoscored.com/) provides a variety of in-game statistics for players. Average stats for players for a season can be found on team pages ([example](https://www.whoscored.com/Teams/133/Show/Turkey-Besiktas)). Following stats has been used for evaluation:

**Summary Stats**
- **games_played:** Number of games played (Matches which the player has been substituted on also count as 1).
- **yellow_cards:** Number of yellow cards accumulated.
- **red_cards:** Number of red cards accumulated.
- **man_of_the_match:** Number of games the player has been determined as the Man of the Match.
- **aerials_won:** Aerial duels won per game.

**Defensive Stats**
- **tackles:** Tackles per game.
- **interceptions:** Interceptions per game.
- **fouls:** Fouls committed per game.
- **offsides_won:** Offside won per game.
- **clearances:** Clearances per game.
- **dribbled_past:** Dribbled past per game.
- **blocks:** Outfielder blocks per game.
- **own_goals:** Total own goals.

**Offensive Stats:**
- **goals**: Total goals scored.
- **assists**: Total assists.
- **shots**: Shots per game.
- **key_passes**: Key passes per game.
- **dribbles**: Dribbles per game.
- **fouled**: Fouled per game.
- **offsides**: Offsides per game.
- **dispossessed**: Dispossessed per game.
- **bad_controls**: Bad controls per game.

**Passing Stats:**
- **passes**: Passes per game.
- **pass_accuracy**: Pass success percentage.
- **crosses**: Crosses per game.
- **long_balls**: Long balls per game.
- **through_balls**: Through balls per game.

Player stats has been acquired from following leagues:
- Argentina Superliga (2017-2018)
- Brazil Série A (2018) (in season, Jul 2018)
- England Premier League (2017-2018)
- France Ligue 1 (2017-2018)
- Germany Bundesliga (2017-2018)
- Italy Serie A (2017-2018)
- Netherlads Eredivisie (2017-2018)
- Portugal Liga NOS (2017-2018)
- Russia premier League (2017-2018)
- Spain La Liga (2017-2018)
- Turkey Süper Lig (2017-2018)

## 2. Methods

### 2.1. Extracting Data
(Notebook: [knn_scout_crawler.ipynb](knn_scout_crawler.ipynb))

Selenium WebDriver API has been used to navigate across team pages to get player stats automatically.

In order to reach player stats in an automated way, for all given leagues, league page url has been navigated to collect team urls from league table. Then all team urls has been navigated in a loop and each team page navigated 4 times for 4 different stat types (summary, defensive, offensive, passing).  

### 2.2. Transforming Data
(Notebook: [knn_scout_transform.ipynb](knn_scout_transform.ipynb))

First, irrelevant attributes like player name, country, age etc. has been dropped from data. Also, goalkeepers removed from data since most of the stats are related to outfield players.

Most important problem is that some players are being transferred between teams during mid-season transfer window. Thus, those players will be added to data 2 times with different stats. Stats for those players should be aggregated accordigly.

Another problem is, some attributes are per game averages while some attributes are total number of occurrences. Those total numbers should be divided by number of games played to acquire per game numbers.

Third problem to solve is, some attributes tend to have higher numbers whilst some attributes tend to have lower. For example, passing is very likely to occur in a game and players most probably will have high number of passes per game. But offside is rarely to occur and players will have a low number of offsides per game. This will cause a bias and algorithm will evalute players by passes per game more than other attributes. Simply dividing all numbers in a column by maximum number in that column will solve the problem. All values will be something between 0 and 1.

### 2.3. Applying Algorithm
(Notebook: [Scout.ipynb](Scout.ipynb))

Nearest Neighbors algorithm in scikit-learn has been used to find players who has similar playing style with a given base player. The algorithm simply calculates distances between a new point (in this case, base player) and a given set of points (all players except base player) and return k number (in this case, 10) of closest points. It's like calculating closest points among scattered points in a 2-d plane for a specific point, but in this case it's an n-dimensional space (n is number of attributes).

Passing player data and base player to the algorithm is enough, scikit-learn does the rest of the job.  

## 3. Results



## 4. Resources
