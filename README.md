# MIST4610-Project1-Group6

## Team Name: 
61608 Group 6

## Team Members:
1. [Askari, Ali](https://github.com/AwpDemon/MIST-4610)
2. [Bloom, Kate](https://github.com/kateabloom/first)
3. [Oggu, Stephen](https://github.com/SpeedRacerAMG/MIST4610_group)
4. [Paul, Ryan](https://github.com/ryanpaul434/MIST-Group)
5. [Stewart, Whitman](https://github.com/whitnotmax/MIST4610-Project1-Group6)

## Problem Description:

We designed the Boxing Management Database to take the sport of professional boxing and take the components of the boxers, the trainers, the fights, the gyms, and the relationship between them. We wanted to use this project as an opportunity to dive into data modeling and SQL in a way that was engaging and interesting to us and our audience. Boxing’s long history and deep talent pool made it the perfect subject, giving us plenty of interesting data to structure and analyze.


## Data Model:

The boxer entity is the primary entity in our data model, and contains attributes such as: name, date of birth, fight record (win, loss, knockout) and trainer. The trainer entity tracks the coaching staff with a one-to-many relationship as it defines experience and achievements. One trainer can have many boxers, but a boxer can only have one main trainer. The fightentity stores information regarding upcoming and historical fights, including the fighters, venue, and fight result. It has a many to many relationship with boxer entity, as multiple boxers fight in different fights and in each fight only two boxers compete against each other. Gym entity contains information about the training facility such as owner, location, membership cost, & related trainers. The relationship between gyms and trainers is one to many as a trainer may work at multiple gyms. Last but not least, performance is tracked through the relationships of boxers, fights and trainers. This requires the fact-based examination of individual boxers fight records, the influence of any trainer, and even the gym in which they train, a systematic approach to boxing management not before possible.


![Data_Model](https://i.imgur.com/4MXGfEC.png)

## Data Dictionary:
![Data_Dictionary](https://i.imgur.com/YuOUm5z.png)
Boxers are the main points of action in the fight. Each boxer is given a unique boxer ID, which is our primary key. We’ve recorded PII’s such as first and last name and which are both VARCHAR, with a data type size cap of 45. Their date of birth is recorded also. Additionally, we track the records of the boxers in this area including wins, losses, and knockouts. 



![Data_Dictionary](https://i.imgur.com/yNjY4Zj.png)
The fight table stores information about boxing matches. Each fight has a fight ID, which serves as its primary key. We store other information about the fight, like its date, address, city, state, weight class, and the number of rounds scheduled. This table helps track details of boxing matches, including location, weight class, and duration, making it essential for fight history records and analysis.



![Data_Dictionary](https://i.imgur.com/RZ0YNI2.png)
The Boxer_Fight table connects boxers and fights, as it’s a many to many relationship, enabling us to use a boxer_id to track a boxer's fight history and a fight_id to access specific fight details.



![Data_Dictionary](https://i.imgur.com/WJyC1hu.png)
In the “trainer” entity, we have included the column name, a description of what each id means, what data type each is classified as, the size of the data type, and the different key types visible in the entity. Each trainer is given a specific trainer ID that acts as the primary key, serving as the unique identifier for the trainer. This is formatted as an integer. We’ve also included first and last name, birth date, years of experience, and the amount of championships each trainer has won. This is helpful in determining their tenure and win percentage.



![Data_Dictionary](https://i.imgur.com/nJbouYe.png)
Each gym has a gym ID, which serves as its primary key unique identifier. We store other information about the gym like its name, address, city, state, date established, and the membership fee. Each gym stores the foreign key of the trainer who is assigned to the gym.



## Queries:

1. This query collects the info the the primary key of the fight, the date and what state the fight happened in.

![query1](https://i.imgur.com/RxcABLe.png)

In this scenario, we have sorted all fights that take place in the state of California. This query is justified so that we are able to see what fights happened in hotspots for boxing, such as the state of California which has been a popular destination for boxing fights.
 
 
 
2. This query displays every state and the average membership fee of the state, which is calculated using the AVG() function and GROUP BY, adding a maximum average of $50 that will be displayed.

![query2](https://i.imgur.com/uF284dl.png)

This query gives great insights into how expensive it would be to train in each state, which would be good information to know for a boxer who is considering a move.



3. All gyms in california are discounting their membership fee by 20% due to new state regulations. List the gym name, the original price, and the new discounted price.

![query3](https://i.imgur.com/VaVH0ZP.png)

Since most information is staying the same except the discounted membership fee, we kept the gym_name and state to see what gyms are eligible to reduce their price. This led us to then create a new field for the new discounted fee. We made this query so the boxers can see if maybe a former place they wanted to train at costs less know, and which locations best fall in line with their finances. 



4. This simple query uses columns from the boxer table to count all rows where a boxer has no losses.

![query4](https://i.imgur.com/N3oxOGC.png)

This query is important because it finds the best boxers in our data model. A boxer is among the best of the best if they are truly undefeated, and in this case, two of the boxers in our database are undefeated.



5. This query uses the boxer, fight, and boxer_fight tables to find information about fights Mike Tyson Has competed in. 

![query5](https://i.imgur.com/RFBs8du.png)

This query is useful when it comes to finding information about a specific boxer. Instead of scrolling through a long list of boxers that have competed in all these fights, you can simply sort by first and last name to efficiently find a specific boxer.



6. This query uses the gym, trainer, and boxer tables to find the total number of boxers who are using a gym, sorting table by descending.

![query6](https://i.imgur.com/5tjHnbk.png)

This query would be useful for finding the most popular gym. We decided the most “popular gym” would be determined by the total number of boxers at a particular gym. This is helpful for a boxer evaluating their gym options, trying to get the most value out of their membership fee.



7. This query shows the boxers whose trainers work at the gym with the lowest membership fee.

![query7](https://i.imgur.com/eMpDkJy.png)

This query identifies boxers training at the most affordable gym which helps analyze cost-effective training choices and gym pricing strategies. 



8. Query retrieves the most expensive gym in each state by selecting the gym with the highest membership fee for every state.

![query8](https://i.imgur.com/HaRuiyQ.png)

The query helps compare gym pricing across states, providing insights into regional cost differences and identifying premium gyms in each state. This is also helpful for both boxers and trainers in determining what gyms they’d rather train at, based on their personal financial preferences.



9. This query retrieves the top 5 boxers with the highest knockout percentage by calculating their knockout rate and ordering them in descending order.

![query9](https://i.imgur.com/KLjH2ri.png)

This query is especially useful for finding the deadliest or most aggressive fighter. KO percentage is a valuable metric which is a key indicator of what ratio of fights end in a knockout, an unequivocal blow for the opponent.



10. This query uses the names of trainers, their years of experience, and sums up the amount of wins they have had over the years.

![query10](https://i.imgur.com/PF8NeAK.png)

This query is useful for seeing what boxers have accumulated the most wins over the years. The query shows how good and experienced a trainer is.





## Database information

![table](https://i.imgur.com/yU6vi2a.png)

Database name: ha_group6_crn61608
