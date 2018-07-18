# KNN Scout

## 1. Introduction

Recently, Real Madrid sold Cristiano Ronaldo to Juventus. Who should they sign for a replacement?

Well, data science shows that the best option is to buy **Harry Kane** from Tottenham. Also, Ciro Immobile could be usefull addition to the squad since data science shows that he has similar playing style. Surprisingly, it seems that non-famous 18 years old Newells Old Boys player Enzo Cabrera also has similar playing style with Cristiano Ronaldo. Good prospect for the future, maybe?

In this project, we will use machine learning to try to find football players who has similar playing style with a given base player.

Thanks to [whoscored.com](https://www.whoscored.com/), we have detailed statistics for players. This project is a good example of using KNN Algorithm.

## 2. Data
[whoscored.com](https://www.whoscored.com/) provides a variety of in-game statistics for players. Average stats for players for a season can be found on team pages. Following stats has been used for evaluation:

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
- England Premier League (2017-2018)
- Italy Serie A (2017-2018)
- Spain La Liga (2017-2018)
- Germany Bundesliga (2017-2018)
- France Ligue 1 (2017-2018)
- Portugal Liga NOS (2017-2018)
- Netherlads Eredivisie (2017-2018)
- Russia premier League (2017-2018)
- Brazil Série A (2018) (in season, Jul 2018)
- Turkey Süper Lig (2017-2018)
- Argentina Superliga  (2017-2018)

## 3. Methods

### 3.1. Getting Data

### 3.2. Transforming Data

### 3.3. Applying Algorithm

## 4. Results

## 5. Resources
