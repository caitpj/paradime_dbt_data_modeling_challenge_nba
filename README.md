# dbt™ Data Modeling Challenge - NBA Edition

# Cai Parry-Jones's Submission

## Table of Contents
1. [Introduction](#introduction)
2. [Data Sources](#data-sources)
3. [Methodology](#methodology)
   - [Tools Used](#tools-used)
   - [Applied Techniques](#applied-techniques)
4. [Visualizations](#visualizations)
   - [Team Playoff Appearances](#team-playoff-appearances)
   - [Player Playoff Games](#player-playoff-games)
   - [Top Playoff Scorers](#top-playoff-scorers)
   - [Top Regular Season Scorers](#top-regular-season-scorers)
   - [NBA Players by University](#nba-players-by-university)
5. [Conclusions](#conclusions)

## Introduction
Explore my project for the _dbt™ data modeling challenge - NBA Edition_, Hosted by [Paradime](https://www.paradime.io/)! This project focuses on answering an all time fan favorite discussion... who... is... the **GOAT**?! More specifically, I focus on providing a direct comparrison of some unique metrics between two giants of the sport: **Michael Jordan**, and **LeBron James**. Although I don't expect this analysis to change the GOAT opinion of fans who have already made up their mind, I hope it will provide some interesting insights unknown to even the most avid **Michael Jordan** and/or **LeBron James** fan, as well as provide fans with some extra amunnition the next time someone questions **Michael Jordan**/**LeBron James** legacy!

### [My GitHub repo](https://github.com/paradime-io/paradime-dbt-nba-data-challenge/tree/cai-parryjones)

## Data Sources
My analysis leverages four key NBA datasets from Paradime:
- *PLAYER_GAME_LOGS*
- *TEAM_STATS_BY_SEASON*
- *COMMON_PLAYER_INFO*
- *PLAYER_SALARIES_BY_SEASON*

I have also used open access USD inflation data:
- *HIST_INFLATION*. Citation: “$1 in 1800 → 2024 | Inflation Calculator.” Official Inflation Data, Alioth Finance, 13 Feb. 2024, [https://www.officialdata.org/us/inflation/1800?amount=1](https://www.officialdata.org/us/inflation/1800?amount=1)

## Methodology
### Tools Used
- **[Paradime](https://www.paradime.io/)** for SQL, dbt™, and data lineage.
- **[Snowflake](https://www.snowflake.com/)** for data storage, ingestion, and computing.
- **Tableau** for data visualization.

### Applied Techniques
- Snowflake to ingest suplementary USD inflation data from csv file
- SQL and dbt™ to transform mentioned data sources to two data marts: player_careers and player_seasons
  - This can best be highlighted using Paradime's [Data Lineage](https://www.paradime.io/graph-lineage)
  - player_careers: <img width="1255" alt="Screenshot 2024-02-24 at 20 04 21" src="https://github.com/caitpj/test_nba/assets/97813242/14c49321-9d3b-475b-b31d-e93da9e0f33a">
  - player_seasons: <img width="1259" alt="Screenshot 2024-02-24 at 20 08 09" src="https://github.com/caitpj/test_nba/assets/97813242/0edfbac1-83d0-414b-b618-633db0e9fc7d">



## Visualizations
### Team Playoff Appearances
Visualization of playoff appearances for all 30 NBA teams, including their playoff appearance rates.

![Team Playoff Appearances](https://github.com/paradime-io/paradime-dbt-nba-data-challenge/assets/107123308/cd69a2fa-6b60-44de-b8bc-2f6a6828f033)

*Insights:*
The Los Angeles Lakers' dominance in playoff appearances, and the San Antonio Spurs' highest playoff appearance rate.
The Spurs have only missed the playoffs 9 times!

### Player Playoff Games
Assessment of NBA players with the highest number of playoff game wins and their win percentages. The '*' next to NBA Player name indicates if they're 
a member of the [NBA Greatest 75 Team](https://www.nba.com/news/nba-75th-anniversary-team-announced)

![Player Playoff Games](https://github.com/paradime-io/paradime-dbt-nba-data-challenge/assets/107123308/ffd6abf3-b8a8-411f-a0be-12402a5d1b45)

*Insights:* 
LeBron James has the most playoff wins of any player, but here's what's most interesting: 
Of the 25 players with the most playoff wins, only 12 of them are members of the [NBA Greatest 75 team](https://www.nba.com/news/nba-75th-anniversary-team-announced). 
There are several players listed that impact playoff wins and compliment their team's best players, but aren't known 
as on the the all time greats, such as: Derek Fisher, Robert Horry, Danny Green. 

### Top Playoff Scorers
Showcases players who achieved the the most points scored in any playoff season.

![Top Playoff Scorers](https://github.com/paradime-io/paradime-dbt-nba-data-challenge/assets/107123308/db51f47a-5cfb-431c-9c7b-3a793a6b4352)

*Insights:* 
Michael Jordan, LeBron James, and Kobe Bryant are the only players having three seasons within the top 25 
highest most points scored in a playoff season.

### Top Regular Season Scorers
Highlights NBA players who scored the most in regular seasons.

![Top Regular Season Scorers](https://github.com/paradime-io/paradime-dbt-nba-data-challenge/assets/107123308/774223ad-11f0-4202-817f-5a8c1daf3afc)

*Insights:* 
Wilt Champerlain is one of the best regular season scorer of all time. In addition to having the most points scored 
in any regular season ever (4,029), he also has six season in the top 25. The only other player with 6 top 25 seasons is Michael Jordan.
In the chart above, notice that Wilt Champerlain doesn't appear once in the top 25 playoff scorers of all time 👀.

### NBA Players by University
Displays which universities have produced the most NBA players.

![NBA Players by University](https://github.com/paradime-io/paradime-dbt-nba-data-challenge/assets/107123308/e21af17a-9cb8-491a-8e0d-b70eae118324)

*Insights:* 
Kentucky has produced the most NBA players in NBA history by a significant margin.... Go Wildcats! Also, this data is [slightly inaccurate](https://erudera.com/resources/colleges-with-most-nba-players/), but that's the NBA API's fault, not mine 🤣

## Conclusions
This project successfully extracts significant insights from NBA data that NBA fans would find interesting, such as: 

- The dominance of teams like the Los Angeles Lakers and the San Antonio Spurs in playoff appearances
- The critical role of "role" players, as highlighted by the playoff games by player insights,
- The extraordinary achievements of players like LeBron James, Michael Jordan in the playoffs, and Wilt Chamberlain in the regular season. 
- The influence of universities like Kentucky in producing NBA talent.
