# Exploratory Analysis of RAPTOR Metrics in the Modern NBA

## Project Overview
RAPTOR (Robust Algorithm (using) Player Tracking (and) On/Off Ratings) is a modern-day plus-minus statistical analysis developed by FiveThirtyEight. This system measures the number of points a player contributes to his team’s offense/defense per 100 possessions, relative to a league-average player. Our team analyzed the `latest_RAPTOR_by_team.csv` (play-by-play metrics from the 2022-2023 NBA season) and the approximate `historical_RAPTOR_by_team.csv` charts (predictive analyses dating from 1977-2022) uncovering comparisons between both sets of data across a variety of criteria. 

## Installation and Usage Instructions of Libraries/Tools
We are utilizing two datasets within FiveThirtyEight's RAPTOR database:

- [Latest RAPTOR Analytics by Team](https://projects.fivethirtyeight.com/nba-model/2023/latest_RAPTOR_by_team.csv) 
- [Historical RAPTOR Analytics by Team](https://github.com/fivethirtyeight/data/blob/master/nba-raptor/historical_RAPTOR_by_team.csv) 

### Required Libraries:
- Pandas
- Numpy
- Matplotlin
- Scipy, stats module
- Seaborn
- Plotly.graph_objects
- Plotly. express
  
### Tool(s) required:
- Jupyter notebook, pyviz environment
  
## Intro
RAPTOR (Robust Algorithm (using) Player Tracking (and) On/Off Ratings) is a modern-day plus-minus statistical analysis developed by FiveThirtyEight. The main component of this system measures the number of points a player contributes to his team’s offense/defense per 100 possessions, relative to a league-average player.  

***Why RAPTOR?***    

RAPTOR fulfills two long-standing goals:
1. To create a publicly available statistic that takes advantage of modern NBA data, specifically player tracking and play-by-play data that isn’t available in traditional box scores.
2. Relatedly, a statistic that better reflects how modern NBA teams actually evaluate players.

## Project Goals
- Does the amount of possessions per player greatly impact that player’s overall RAPTOR ratings? Why or why not?
- Which team displayed the highest/lowest RAPTOR ratings across the 2022-23 season across all players? How does this data compare to their predictive PREDATOR model?
- How accurate are the overall results of predictive-RAPTOR, which was used for the historical data charts (1977-2013), compared to those of modern-RAPTOR’s integration (2013-Present)? 
- Is there a relationship between the most minutes played and the greatest pace impact on the team compared to RAPTOR scores?
- How do these statistics line up by player in relation to the top players/teams (MVPs) of the 2022-2023 season?
- Find out the relationship between different features.

## Data Cleaning
- There are two separate datasets for this challenge, the historical dataset which includes data from 1977-20xx, and the latest dataset which is for 2023.  
- The first step was to import the datasets and then merge them into one sheet.
- Then, the datasets were checked for null values. There were some null values under historical data, which were then filled and checked for duplicates, finally giving us our clean dataset to work with.
  
## Analysis
After merging and cleaning the datasets, we defined some functions which were used throughout our notebook.   

We started our data exploration by looking at the average distribution of the PREDATOR total, RAPTOR total, and WAR total. ![histogram](/Visuals/histogram.png) 

Our main goal was to evaluate how different variables influence the RAPTOR scores and if there is a correlation between those and to compare the RAPTOR results to actual results. ![Correlation](/Visuals/corr.png)

- Predator total and Raptor total have the strongest correlation
- Raptor total and pace impact have the weakest correlation
- War total and minutes played have a strong correlation
- Raptor total and possessions have a weak correlation.  

The first variable we looked at was the number of possessions per player. We did this by creating a scatter plot and a regression line, which showcased a weak, but positive correlation. ![Linear Regression - Poss](/Visuals/avg_poss_teams.png)

Along with the number of possessions, minutes played also play an important role in a player's performance when we compared average minutes played by a player with their RAPTOR scores we found out that there was a weak positive correlation as well.  

Lastly, we wanted to compare a player's pace impact on their team with their RAPTOR scores, we uncovered a negative correlation. We can conclude that although RAPTOR scores are affected by the number of possessions and the minutes played, it isn't a strong correlation. 

Now that we had covered individual RAPTOR scores, we wanted to look at the teams. We continued looking at a team's highest and lowest RAPTOR scores across the 2022-2023 season and compared them to their PREDATOR scores. Atlanta Hawks ranked first and Portland Trail Blazers ranked last. For the PREDATOR top was the Cleveland Cavaliers and the bottom was the Portland Trailblazers. The PREDATOR analysis predicted Portland correctly and Cleveland was third overall. 
![Top_10_Mean_Raptor](/Visuals/Top_10_Mean_Raptor.png) 
![Bottom_10_Mean_Raptor](/Visuals/Bottom_10_Mean_Raptor.png)
PREDATOR is a similar statistic to RAPTOR which is PREDictive rApTOR according to Fivethirtyeight. Fivethirtyeight lists what a player’s PREDATOR score is based on: Age, Draft position, NBA career length, Height, Weight, Position, and Recent All-NBA, MVP and All-Star appearances. For Rookies heading into their first season, the data also considers the college program, international league. Without going further into detail with individual statistics, the data collected shows the average of the PREDATOR score per team. It was found that CLE(Cleveland Cavaliers) were suppose to have the highest RAPTOR total. For RAPTOR they finished in 3rd.  They finished the season in 4th place with 51 wins and 31 losses. The PREDATOR model showed POR(Portland Trail Blazers) being last. If the analysis just had these two teams, you could say there was a strong positive correlation to good and bad teams for RAPTOR and PREDATOR. However, the top 10 teams and the bottom 10 teams, there is a positive correlation with the lower teams than higher teams. When looking at the average and above average teams, we can see some inconsistencies in the analysis. The reason for strong correlation for bottom teams with RAPTOR and PREDATOR with bottom teams is the absence of measuring team chemistry, team playstyle and coaches’ chemistry with players. It would be reasonable to get the bottom teams more accurate because they do not have those characteristics in the first place. 

Next, we wanted to look at how accurate the overall PREDATOR was which was used for the historical dataset when compared to modern RAPTOR integration.  

The average RAPTOR total with the latest data shows more trends because starting from 2013-14 player-tracking data became available online. The historical data uses a limited range of variables. With more data available, more accurate readings can be done as shown.  

Lastly, we wanted to evaluate How do these statistics line up by player in relation to the top players/teams (MVPs) of the 2022-2023 season.

The RAPTOR metrics used to identify the top players and teams were raptor total, raptor box total, raptor offense, raptor defense, raptor on/off total, war total, minutes played, and possessions. Our statistical results line up with the top players and top teams for the 2022-2023 season. Our top player result is the NBA finals MVP and the top team result won the championship this season.

The top player for the 2022-2023 season is Nikola Jokic and the top team for the 2022-2023 season is the Denver Nuggets.

## Visuals

![Boxplot](/Visuals/Boxplot.png)  
- Overall, LeBron has the highest peak-RAPTOR score, while Magic’s was the most consistent
- Of these players, Chris Paul has the widest range of RAPTOR scores
- Kobe Bryant’s 2014 (RS) total RAPTOR score is -6.28, compared to his highest of 9.08
- LeBron’s total RAPTOR score of 16.07 in 2009 (PO) is the highest ever recorded

![Lebron](/Visuals/Lebron.png)
![Without Lebron](/Visuals/Lebronless.png)  

With the removal of LeBron James, the RAPTOR total per team decreases for every season. Therefore, higher-profile players like LeBron James have the ability to askew the RAPTOR total.

![LeBron vs Kobe Line Plot](/Visuals/lk.png)


## Major Findings
- Predator total and Raptor total have the strongest correlation
- Raptor total and pace impact have the weakest correlation
- War total and minutes played have a strong correlation
- Raptor total and possessions have a weak correlation

RAPTOR fuels actual team/player performance, whereas PREDATOR fuels projections of team/player performance. Variables are essentially the same across, but FiveThirtyEight avoided poorly performing variables in out-of-sample testing when constructing RAPTOR, initially.

- If we look at individual total RAPTOR scores, John Stockton is at number 1, whereas for the average RAPTOR score, it is Stanley Umude.
- Overall, LeBron has the highest peak-RAPTOR score, while Magic’s was the most consistent.
- Of these players, Chris Paul has the widest range of RAPTOR scores.
- Kobe Bryant’s 2014 (RS) total RAPTOR score is -6.28, compared to his highest of 9.08.
- LeBron’s total RAPTOR score of 16.07 in 2009 (PO) is the highest ever recorded.

## Limitations
- Advanced metrics
- Poor performing out-of-sample variables in constructing RAPTOR are avoided for PREDATOR.
- We didn't consider regular season (RS) and playoff (PO) stats are two separate entities often, like within the datasets.
- Various specifics such as coaching styles, team strategies, and the utilization of only larger sample sizes. 
## Conclusions

- Total PREDATOR and RAPTOR scores have the strongest correlation among all metrics
RAPTOR includes a plethora of descriptive data types that are typically player-specific but can be utilized to uncover data through individual player statistics, as well as from a team POV.
-RAPTOR and PREDATOR are more accurate with losing teams than winning teams becasuse they do not account for team chemistry and 
- Individual players can drastically impact a team’s average and total RAPTOR scores.
- There are specifics RAPTOR doesn’t vibe with as a predictive tool, such as utilizing smaller sample sizes, varying coaching styles, team strategies, and overall pace impact.
- FiveThirtyEight’s RAPTOR model is a robust and intuitive choice for those looking for a more in-depth way of measuring individual player-tracking ability, as well as play-by-play data.


## References 
For dataset:
[FiveThirtyEight](https://fivethirtyeight.com/features/how-our-raptor-metric-works/)
  [More FiveThirtyEight](https://www.basketball-reference.com/about/bpm2.html)
  [for importing image](https://mljar.com/blog/jupyter-notebook-insert-image/)
  [Seaborn](https://seaborn.pydata.org/)
  [Plotly](https://plotly.com/python/)  
Specific debugging and code references are included in comments before the code.

## Team Members
- [Christopher](https://github.com/cbake105)
- [Jack](https://github.com/jackhayes21)
- [Jonathan](https://github.com/jccrock311)
- [Uzma](https://github.com/UzmaSayyeda)
- [Wipawadee](https://github.com/wnaiyakhu)
