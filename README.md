# dbt™ Data Modeling Challenge - NBA Edition

# Submission by Cai Parry-Jones

<img width="627" alt="image" src="https://github.com/caitpj/test_nba/assets/97813242/664e054c-567f-4c7b-8efe-b4d7594c6090">


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
Explore my project for the _dbt™ data modeling challenge - NBA Edition_, Hosted by [Paradime](https://www.paradime.io/)! My project focuses on answering an all time fan favorite discussion... who... is... the **G.O.A.T.**?! More specifically, I focus on providing a direct comparrison of some unique metrics between two giants of the sport: **Michael Jordan**, and **LeBron James**. Although I don't expect this analysis to change the opinions of fans who have already made up their mind, I hope it will provide some interesting insights unknown to even the most avid **Michael Jordan** and/or **LeBron James** fan, as well as provide fans with some extra ammunition the next time someone questions **Michael Jordan**/**LeBron James**'s legacy!

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
  - I use [dbt's method](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview) to structure the data models
    - **Staging** — our initial modular building blocks, from source data, just tiddied up a bit
    - **Intermediate** — stacking layers of logic with clear and specific purposes to prepare our staging models to join into the entities we want
    - **Marts** — bringing together our modular pieces, ready to be used for analysis
  - This can best be highlighted using Paradime's [Data Lineage](https://www.paradime.io/graph-lineage)
  - player_careers: <img width="1255" alt="Screenshot 2024-02-24 at 20 04 21" src="https://github.com/caitpj/test_nba/assets/97813242/14c49321-9d3b-475b-b31d-e93da9e0f33a">
  - player_seasons: <img width="1259" alt="Screenshot 2024-02-24 at 20 08 09" src="https://github.com/caitpj/test_nba/assets/97813242/0edfbac1-83d0-414b-b618-633db0e9fc7d">



## Visualizations
### Player Pay
The salary of players is a critical aspect of how players' team/s value them, as well as more generally defining a player's personal success. It is a career for them after all.

![image](https://github.com/caitpj/test_nba/assets/97813242/5284c08a-b059-486f-95fc-a6640b16dad9)


*Insights:*
When we take inflation into consideration, it is clear Michael Jordan was, by far, payed more than any other player in NBA history for a single season... not once, but twice! What's perhaps more suprising is despite this, LeBron James has accumulated almost 3 times more in total salary pay over his career — and counting. This was achieved through longevity of career, LeBron James has (currently) played 21 season in the NBA, compared to Michael Jordan's 15, as well as consistently earning a high, yet not record breaking salary year-on-year. Despite Michael Jordan's two astronomical salaries in the 1996-97 and 1997-98 seasons, he only averaged $11m a year in NBA salary, compared to LeBron James's $24m.

_Limitation of analysis_: It's important to note that NBA salary is not the only income source of NBA players, especially those of Michael Jordan and LeBron James's calibre. Other sources include: endorsement deals, merchandise sales, investments, and media & broadcasting.

### Key Game Statistics
Here are a few of the critical metrics that represent a players performance in games over their career. Note, the '*' next to the Other legend means: any other NBA player who had played an average of 25 minutes per game during their career.

![image](https://github.com/caitpj/test_nba/assets/97813242/6388c03c-bb09-43f4-a30a-26b00a5ec82a)


*Insights:* 
Michael Jordan has scored more points per game, and won more games as a % of total games played than LeBron James. What's more, Michael Jordan switches in to hyperdrive when he's in the playoffs, with a 17% higher points scored per game vs LeBron James, a 3% higher proportion of games won vs LeBron James, and a staggering 57% higher average plus-minus per game vs LeBron James. On the other hand, LeBron James does have a higher average plus-minus per game during the regular season, where the bulk of games are player. A LeBron James fan could argue that the staggering difference in average plus-minus per game for Michael Jordan between playoff games and regular season games highlights Michael Jordan was lucky to have performed so well in the playoff games. If he had perfromed in the playoffs as he had in the regular season, he would likley not have won nearly as many playoff games and subsequently achieved fewer NBA Championships.

_Limitation of analysis_: Sadly the plus-minus data only becomes available after the 1995-96 season. Which means it only captures four of Michael Jordan's 15 seasons in the NBA.

### Key Game Statistics by Season
It's not great careers that win you Championships, it's great seasons. The following visualisations aim to shine a light on the outstanding seasons of Michael Jordan and LeBron James, as well as highlight their consistency of outperfroming fellow NBA players. The '*' next to the Other legend means: any other NBA player who had played an average of 25 minutes per game during the season.

![image](https://github.com/caitpj/test_nba/assets/97813242/b9bdcb9d-4986-4395-a0aa-57a6b4a1520a)

![image](https://github.com/caitpj/test_nba/assets/97813242/a1e84159-7740-4271-844e-208ce59edd2c)

![image](https://github.com/caitpj/test_nba/assets/97813242/9d3ff3e8-acea-4ff4-a805-e65fbb7005f2)


*Insights:* 
Michael Jordan and LeBron James both consistently 

### Top Regular Season Scorers
Highlights NBA players who scored the most in regular seasons.


*Insights:* 
Wilt Champerlain is one of the best regular season scorer of all time. In addition to having the most points scored 
in any regular season ever (4,029), he also has six season in the top 25. The only other player with 6 top 25 seasons is Michael Jordan.
In the chart above, notice that Wilt Champerlain doesn't appear once in the top 25 playoff scorers of all time 👀.


## Conclusions
This project successfully extracts significant insights from NBA data that NBA fans would find interesting, such as: 

- The dominance of teams like the Los Angeles Lakers and the San Antonio Spurs in playoff appearances
- The critical role of "role" players, as highlighted by the playoff games by player insights,
- The extraordinary achievements of players like LeBron James, Michael Jordan in the playoffs, and Wilt Chamberlain in the regular season. 
- The influence of universities like Kentucky in producing NBA talent.
