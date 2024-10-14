# Team 8 Mist 4610 Group Project 1

## Team Name: 
select * from MIST4610 where grade = A; 

## Team Members:

1. Gus Wilkerson [@augwilk](https://www.github.com/augwilk)
2. Emma Calleja [@EmmaCalleja](https://github.com/EmmaCalleja)
3. Hannah Conley [@Hmc98563](https://github.com/Hmc98563)
4. Rahil Patel [@rahilp0215](https://github.com/rahilp0215)
5. Marc Ordonio [@marcord245](https://github.com/marcord245) 


## Problem Description:

The task at hand:
Today, college football data is spread across multiple platforms and sources, making it difficult to get a clear and accurate picture of the sport. Since this approach is broken up across platforms, it is difficult to access and analyze key statistics or trends over time. To address this issue, the NCAA has launched a project to create an essential database of Division 1 college football statistics.
Specifically, the project aims to create a unified data repository for all D1 conferences, players, and head coaches, including in-depth statistics such as NIL, wins, losses, and game statistics among others.


## Data Model

Explanation of data model: 

Our data model is based around the landscape of college football as we see it. College football is made up of a handful of conferences each of which has several teams as shown by the one to many relationship established between the conference and team entities. The team entity contains pertinent information for a specific team including what university of the team and the tally of their wins and losses.

Teams need several coaches to operate (i.e. position coaches, coordinators, trainers) but each has just one head coach as shown by the one to one relationship between the coach and team entities. Coaches have a name, a salary, and a title of their position.

Each team plays in multiple games in a year and each game has two teams. The weak entity linking the many to many relationship between team and game is the team_game entity which stores each team’s individual score in the specific game. 

Because of the transfer portal, players can now be on multiple teams over the time of their collegiate career but only one team at a time. The portal entity links many players to many teams and vice versa, storing the date they joined and left the team if applicable. 

The player table stores personal information for each player such as their name, birthdate, number, and position. A player plays in many games and a game has many players involved. The weak entity between these two entities is gameStats which stores the offensive yardage statistics each player records in each game they play. Passing yards, receiving yards, and rushing yards for each player are stored here.

A player can also now have many NIL deals with several companies. One company (stored in the Sponsor table) also has the ability to sponsor many players. A sponsor has a company name and a unique id. To link the many to many relationship between Sponsor and player there is the NIL table. The NIL table stores the id of the deal as well as the agreed upon dollar amount for the contract between a company and a player.

Our data model stores a range of data regarding college football which could be useful for a school administration, third party company interested in sponsoring athletes, or the everyday college football fan!



![Project Diagram](https://github.com/user-attachments/assets/e39815d3-a0fe-4377-876d-d4131b634156)

## Data Dictionary:
![Screenshot (72)](https://github.com/user-attachments/assets/82634b2b-0daf-4d5b-b2d9-45b62b11f1eb)

![Screenshot (73)](https://github.com/user-attachments/assets/f834ddce-d98a-4289-b05a-091d4bfe146f)

![Screenshot (74)](https://github.com/user-attachments/assets/cbd29dbd-fec7-40c4-9b17-bcdd424f8c47)

![Screenshot (75)](https://github.com/user-attachments/assets/55f7ca9e-76d2-49e3-a339-c9880c859719)

![Screenshot (77)](https://github.com/user-attachments/assets/22b193fd-f661-43c9-963a-4435a12a9ecd)

![Screenshot (78)](https://github.com/user-attachments/assets/6525768b-ea41-49a6-ba09-3431e74f6bbf)

![Screenshot (80)](https://github.com/user-attachments/assets/01c66565-38a3-46e5-986d-9146cf72e75c)

![Screenshot (85)](https://github.com/user-attachments/assets/bcf0973f-fbda-4a77-8568-42ee1d11532b)

![Screenshot (86)](https://github.com/user-attachments/assets/7d285e9e-2eb4-442b-a8ff-3f0dbc14ed91)

![Screenshot (87)](https://github.com/user-attachments/assets/a125aa6f-7d8e-4784-a3d1-74155a016e1a)


## Query Type Matrix:

![Screen Shot 2024-10-13 at 8 29 41 PM](https://github.com/user-attachments/assets/cf262f29-f47f-43a4-8608-b380128479d1)



## Queries:

1. Query 1 lists the players that have NIL deals with the company Nike along with their cummulative statictics for teh season. The results are ordered from greatest to least stats with priority given to passing yards and then receiving yards. 

![Screenshot (63)](https://github.com/user-attachments/assets/861b5818-259b-41e1-bf08-48344921dfaa)

Query 1 allows managers to see which signed players are perfroming the best. A company like Nike would want to sign with the highest producing atheletes to help build their brand as an elite sporting wear producer. The company may need to consider cutting deals with certain athletes that are nto perfroming well or look into extending contracts with high performing players. This query also reveals areas Nike could continue to grow. For example, Only one player signed with Nike has a significant numebr of rushing yards. This may entice Nike to look into other running backs to sponsor to continue to grow and promote their brand in teh college football landscape. This query could help Sponsors make informed decsions and assess how their contracted players are performing.

2. Query 2 shows which head coach and their team exceeded the average number of wins in the SEC.

![3](https://github.com/user-attachments/assets/07b962b5-4bf0-4433-8f26-094ad190250b)

Query 2 allows managers to look at statistics for performance benchmarking and rankings within the SEC. This can also be used as a head coach evaluation to see which head coach and their team is exceeding above average with this conference. An athletic director, fro example, who is in charge of hiring and firing coaches may want to review this data to see how their coach is performing relative to other coaches in the conference. This query might help an anthletic department make informed descions on their coach's salary, job security, or future contracts.

3. Query 3 shows the stats of players with over 500 passing yards who are not signed to an NIL deal

![Screenshot (89)](https://github.com/user-attachments/assets/66c55119-b0ba-475f-8c11-3ff2a9aef43a)

Query 3 allows both Sponsors and players to see which players may be highly productive on teh field but don't yet have an NIL deal in place. This informs potential sponsors about the best candidates fro future deals. A company woudl want to find teh best atheletes to promote their brand and being able to pick out players taht don't yet have a contract signed will help raise the lieklyhood that they are able to close a deal.

  
4. Query 4 retrieves all players and the team they joined, along with the date they joined, ordered by descending dates.
 
![querey for college footbal 2 complex](https://github.com/user-attachments/assets/5427cb77-9df4-4405-b9e4-eda3931c5de3)

With query 4, managers will find this data useful for several reasons, particularly in the context of player management, team performance, and strategic decision-making. This allows a comprehensible table to showcase these statistics through this one platform. Thsi woudl be useful in a scenario where a coach would be monitoring their player overturn. If tehy were to review this data and see that many players had joined their team recently relative to otehr teams they might be concerned taht their roster is made up of young adn inexperienced players. On teh otehr hand, if a new player as not joined their team in quite some tim ethey may wan tot ivent more resources in recruiting.

Query 5 highlights all of the players that have the most combined recieving and rushing yards in all of the conferences

<img width="842" alt="QUERYMIST" src="https://github.com/user-attachments/assets/444e8a4e-0529-4881-a7b7-e4b2f45ba1af">
<img width="388" alt="Screenshot 2024-10-13 at 8 38 48 PM" src="https://github.com/user-attachments/assets/c5db8c73-74d0-4ded-ad9f-50fc69c60ee6">


Query 5 allows managers to look at the statistics for the performance of the offensive players, moving the spotlight away from the QB position. It can be also used by Head coaches to see who are the best playmakers are in the offence in comparision to other players, which can be valubale in developing different schemes against different teams. For example, it can tell a head coach what player is exceeding compared to other offensive players that aren't neccesarily the QB, and make informed and thorough decisions on who the ball should be given to mainly, impacting the performance of the whole offense. 

Query 6 highlights conferences with cumulative win/loss ratios higher than average. 

![image](https://github.com/user-attachments/assets/4325dc9b-e027-4d52-aeb2-d0e12fdabfe1)

Query 6 helps managers identify which conferences are performing the best. This information is valuable for recruiting strategists, as it allows them to adjust their pitches and incentives based on their conference’s ranking. Higher-performing conferences naturally attract more interest from high school recruits. Additionally, strong conference performance plays a crucial role in securing media coverage and sponsorships. Teams in top-performing conferences tend to have larger fan bases, leading to increased revenue from media deals and sponsorship opportunities.

Query 7 shows brands that spend more than average on NIL. 

![image](https://github.com/user-attachments/assets/7b935a27-355d-462f-9702-9f3a16b7c41f)

Query 7 helps managers identify which companies hold the largest shares of the market. This information enables managers to target these major contributors when seeking additional sponsorships. Additionally, tracking companies with above-average market shares is valuable for regulatory purposes, ensuring fair play and equal opportunities.

Query 8 shows the poorest preforming mascots. 

![Screenshot (88)](https://github.com/user-attachments/assets/8f8cea23-1b01-478f-89ec-d56b14ddc157)


Query 8 is useful to managers as part of a marketing strategy. Consistently underperforming teams can use this information to consider rebranding, which may help revitalize fan engagement and, in turn, create new sponsorship opportunities.

Query 9 retrieves information about sports teams and their head coaches, specifically listing the team's name, number of wins and losses, head coach's name, and their salary. The data is sourced from two tables: team and coach. The tables are joined based on a common identifier to combine related information. The results are ordered by the coach's salary in descending order, meaning the highest-paid coaches will appear first.

<img width="467" alt="952x980 png 672cf1addad246bf91b6ee318d118c80" src="https://github.com/user-attachments/assets/e79bb1bf-9968-461e-a5aa-5db0aeded2d3">

This query is valuable for managers as it allows them to assess team performance in relation to coach compensation. By comparing the number of wins and losses with the coach's salary, managers can evaluate the return on investment for each coach. This insight can guide decisions on salary adjustments or the recruitment of new coaching talent. Additionally, ordering the results by salary allows for easy identification of the highest-paid coaches, enabling more informed budget allocation and salary negotiations.


Query 10 identifies top-performing players on successful teams by calculating average rushing yards which would help managers make decisions on player utilization, strategy, and compensation.

<img width="545" alt="Screenshot 2024-10-13 at 7 33 20 PM" src="https://github.com/user-attachments/assets/0c49400c-a80e-42f6-8b80-ce0aa133843d">

This query also filters for players who have participated in at least three games, highlighting consistent contributors that would be eligible. The insights can guide decisions on resource allocation, such as playing time and training. It also supports strategic planning by leveraging players' strengths and optimizing game strategies. Additionally, the data aids in performance-based compensation and player development decisions. The data can also be useful for the committee to decide what players are eligible for college awards based on their performance.









## Database information:

Name of the database: cs_aww39979

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: 
CALL TP_Q1();
