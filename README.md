# dbt™ Data Modeling Challenge - NBA Edition
# The G.O.A.T. Debate - Submission by Cai Parry-Jones

<img width="627" alt="image" src="https://github.com/caitpj/test_nba/assets/97813242/664e054c-567f-4c7b-8efe-b4d7594c6090">


## Table of Contents
1. [Introduction](#introduction)
2. [Data Sources](#data-sources)
3. [Methodology](#methodology)
   - [Tools Used](#tools-used)
   - [Applied Techniques](#applied-techniques)
4. [Visualizations](#visualizations)
   - [Player Pay](#player-pay)
   - [Key Game Statistics](#key-game-statistics)
   - [Key Game Statistics by Season](#key-game-statistics-by-season)
   - [Body Type](#body-type)
5. [Conclusions](#conclusions)

## Introduction
Explore my project for the _dbt™ data modeling challenge - NBA Edition_, Hosted by [Paradime](https://www.paradime.io/)! My project focuses on answering an all time fan favorite discussion... who... is... the **G.O.A.T.**?! More specifically, I focus on providing a direct comparison of some unique metrics between two giants of the sport: **Michael Jordan**, and **LeBron James**. Although I don't expect this analysis to change the opinions of fans who have already made up their mind, I hope it will provide some interesting insights unknown to even the most avid **Michael Jordan** and/or **LeBron James** fan, as well as provide fans with some extra ammunition the next time someone questions **Michael Jordan**/**LeBron James**'s legacy!

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
- Snowflake to ingest supplementary USD inflation data from csv file
- SQL and dbt™ to transform mentioned data sources to two data marts: player_careers and player_seasons
  - I use [dbt's method](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview) to structure the data models
    - **Staging** — our initial modular building blocks, from source data, just tidied up a bit
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
When we take inflation into consideration, it is clear Michael Jordan was, by far, paid more than any other player in NBA history for a single season... not once, but twice! What's perhaps more surprising is despite this, LeBron James has accumulated almost 3 times more in total salary pay over his career — and counting. This was achieved through longevity of career, LeBron James has (currently) played 21 seasons in the NBA, compared to Michael Jordan's 15, as well as consistently earning a high, yet not record breaking salary year-on-year. Despite Michael Jordan's two astronomical salaries in the 1996-97 and 1997-98 seasons, he only averaged $11m a year in NBA salary, compared to LeBron James's $24m.

_Limitation of analysis_: It's important to note that NBA salary is not the only income source of NBA players, especially those of Michael Jordan and LeBron James's caliber. Other sources include: endorsement deals, merchandise sales, investments, and media & broadcasting.

### Key Game Statistics
Here are a few of the critical metrics that represent a player's performance in games over their career. Note, the '*' next to the Other legend means: any other NBA player who had played an average of 25 minutes per game during their career.

![image](https://github.com/caitpj/test_nba/assets/97813242/6388c03c-bb09-43f4-a30a-26b00a5ec82a)


*Insights:* 
Michael Jordan has scored more points per game, and won more games as a % of total games played than LeBron James. What's more, Michael Jordan switches into hyperdrive when he's in the playoffs, with a 17% higher points scored per game vs LeBron James, a 3% higher proportion of games won vs LeBron James, and a staggering 57% higher average plus-minus per game vs LeBron James. On the other hand, LeBron James does have a higher average plus-minus per game during the regular season, where the bulk of games are played. A LeBron James fan could argue that the staggering difference in average plus-minus per game for Michael Jordan between playoff games and regular season games highlights Michael Jordan was lucky to have performed so well in the playoff games. If he had performed in the playoffs as he had in the regular season, he would likely not have won nearly as many playoff games and subsequently achieved fewer NBA Championships.

_Limitation of analysis_: Sadly the plus-minus data only becomes available after the 1995-96 season. Which means it only captures four of Michael Jordan's 15 seasons in the NBA.

### Key Game Statistics by Season
It's not great careers that win you Championships, it's great seasons. The following visualizations aim to shine a light on the outstanding seasons of Michael Jordan and LeBron James, as well as highlight their consistency of outperforming fellow NBA players. The '*' next to the Other legend means: any other NBA player who had played an average of 25 minutes per game during the season.

![image](https://github.com/caitpj/test_nba/assets/97813242/8997914c-0a35-453c-aa0f-6caa92d315b9)


*Insights:* 
Winning is clearly something both Michael Jordan and LeBron James do more frequently than the average NBA player. And winning games is also something that's highly correlated to winning Championships, who'd have thought, with neither Michael Jordan or LeBron James winning a Championship in a season that had less than a 72% game win ratio. There were three seasons where LeBron James had a higher win ratio than 72%, but failed to win the Championship, while Michael Jordan had zero seasons over this win ratio without landing the Championship. Does that indicate Michael Jordan was luckier than LeBron James? Or was Michael Jordan simply more clinical at finishing the season off on a high?

![image](https://github.com/caitpj/test_nba/assets/97813242/b029e058-2254-4006-b7dd-fe5d59993dd2)


*Insights:* 
Michael Jordan has a higher average points per game, but it's close. Meanwhile, LeBron James has a far higher average total rebounds per game and average assists per game. Might this indicate LeBron James is more of a team player?

![image](https://github.com/caitpj/test_nba/assets/97813242/ed180e22-ed1e-45f3-823e-68cc88eb4f36)


*Insights:* 
Michael Jordan is a bit all over the place when it comes to his defensive stats. For example, in the 1987-88 season he had an impressive 1.5 average blocks per game, but the very next season that stat was cut in half to 0.8 average blocks per game. You'd have thought the player who had been moving teams the most would be changing their average season stats the most, but this appears not to be the case.

### Body Type
There's no question about it, being tall helps your basketball. But was this stat particularly relevant for Michael Jordan and LeBron James in comparison to the rest of the NBA players?

![image](https://github.com/caitpj/test_nba/assets/97813242/48a3155d-1fd8-42cf-abce-47c61d020f2b)


*Insights:* 
Michael Jordan is almost impressively average when it comes to his height and weight compared to the rest of the NBA, while LeBron James in on the heavier and taller side of the NBA scale. A funny point to note is LeBron James has a BMI of 27 according to this dataset. That puts him in the overweight category, and not far off being labeled obese! This is probably more of a point against the BMI metric rather than LeBron James, he looks pretty fit and healthy to me.

_Limitation of analysis_: Height and weight don't tell the whole picture of a player's physicality. For example, body fat %, and injury details. It's also worth pointing out that weight is likely to fluctuate quite a bit during a player's 15+ year career, there is no data on this fluctuation.


## Conclusions
Michael Jordan and LeBron James are both clearly exceptional basketball players. However, from this analysis, I believe the G.O.A.T. title belongs to LeBron James. This is because:
- He is remarkably consistent with his average games stats, season on season, meaning it's less likely LeBron James's success can be attributed to luck.
- Although LeBron has 2 fewer Championships, he has a higher number of seasons with a game win ratio that are expected to win a Championship.
- LeBron has earned 3 times more salary in the NBA than Michael Jordan. Money talks.
- He has a more impressive physicality than Michael Jordan, being 3 inches taller and 34 pounds heavier.

This project extracts significant insights from NBA data, focusing on performances of Michael Jordan and LeBron James. The way the data has been modeled means it is easy to select different players for future analysis. 

