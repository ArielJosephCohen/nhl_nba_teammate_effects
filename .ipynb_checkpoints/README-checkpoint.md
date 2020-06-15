# ***Hart and Soul***

![crosby/lebron](images/crosbylebron.jpg)

# Thank you for visiting my project.

### I will use data science to explore the effects of teammate contributions to individual accolades in sports. I will be placing a particular focus on the MVP award in the NBA and the congruent Hart Trophy award in the NHL.

While both basketball and hockey are complex team sports, it is often believed that any given basketball game can be influenced most strongly by the pressence of one or two key players (think LeBron Durant or Kevin Durant) while more randomness exists in hockey (having a norris trophy-winning defensemen doesn't guarantee the opposition will not score on you). I hope to use data to see how much teammates' contributions matter in the awards for the league's best player. I will be comparing teammate statistics to league averages, looking for trends in player info (such as draft position), and performing other types of statistical inquiries as I work toward my goal of understanding the effect of teammates on individual accolades. I hope to have some stories to tell at the end of this and also would like to have advice for any person trying to understand how to predict who will win awards.

### Searching for data.

I looked all over the internet to find data. I found a lot of NBA and basketball data such as player descriptions and statistics but had trouble finding data about hockey and the NHL. While I initially found a lot of basketball data and spent a lot of time working with it in order to compose a comprehensive data base representing the NBA, I ultimately scrapped that plan in favor of webscraping on a much larger scale. What I mean by this is that my data on advanced stats, for example, only surveyed recent seasons, and other sources were incomplete as well. I created a good webscraping function for hockey and used that to find NBA data. As a result, I lost the subtleties of advanced stats but had a more consistent representation of the NBA across their entire history. As I moved further away from 2020, I lost some data such as blocks which were not recorded in early league days, but there would literally be no way of getting that data. What this means is that the weight of the remaing features, such ass points per game, would contribute more into determining a player's value. I would like to credit the https://www.sports-reference.com/ network of data in many different sports for helping me get my data. One problem / limitation in my collection process, which applied to hockey too was that I didn't account for trades or free agency. If a player was on Chicago and moved to Detroit, my function assigns him to detroit for the entire year. bWith hockey and the NHL, I used https://www.sports-reference.com/ again. At first, I had trouble finding csv files for hockey, but that turned out to be a blessing. I needed to webscrape from the beginning and not tediously merge a bunch of different data frames. Originally, I used one csv for data up to 2018 and webscraped the 2019-19 season. I changed all my data to webscraped data for two reasons. Reason 1: I needed to account for trades and player movement; if a player moves, their team gets designated as "TOT" for total. I wanted to assign the final team a player is on in a season as their team and not lose data for all the players who moved teams. Reason 2: The csv I started with was missing over 20 years of data. Weirdly, the 2005-06 NHL season needed special scraping rules as it recorded traded players differently that all other years. I'd like to quickly note that I created a function for skaters and a function for goalies as they have different stat categories. Interestingly, on https://www.sports-reference.com/ the skater stats remain unchanged between 1918 and 2007, even with missing values, but new stats are added in 2008. Goalie stats stayed the same between 1918 and 2020, which was convenient. This change in skater stats was inconvenient and bothered me for a bit as I was scared that the statistics for skaters would change a lot more than once, but it worked out nicely that they changed only once.

### A bit about the web scraping I did.

#### The website:
![hockey-ref-1](images/nhl-ref-scrape.png)

Creating my webscarping function in the very beginning was an easily scalable function, but was difficult to build. I have little experience with webscraping and needed to do some form of guess-and-check, but worked hard and created a nice and robust function. I'll display part of the function below. While it was robust, some parts of the process were hard to consolidate, so the code is not the most efficient at times, but it works effectively toward the general end goal.

### Here, I will show some code from my data engineering process described above.

![hockey-ref-scrape-goalie1](images/goalie_scrape_func1.png)

a little is cut off - in the middle of the function

![hockey-ref-scrape-goalie1](images/goalie_scrape_func2.png)

### Linking to award winners.

After scraping my data for NBA players, NHL goalies, and NHL skaters to have a complete and comprehensive review of every player in any season (like ever) I saved my data into CSV files so I could use them as I went forward with my project and share the databases I generated with other people. I now understand why people need this data as it appears to be a lot harder to find than I had expected and plan on sharing this data. In addition, having gathered my data, I was now ready to move forward and focus on the teammates of MVP / Hart Trophy winners and finished up all the webscraping by generating a list with every winner, the year they won it, and the team they played for (did you know there was only one player who switched teams mid-season to win the Hart Trophy in NHL history?). I saved those lists to csv files afterward.

![nba-mvp](images/mvp_winners.png)

![hart-winners](images/hart_winners.png)

### Plans versus what actually happened.

When I started this project, I had expected it to move rather quickly. It did not. That has very little to do with the complexity of the project, however. I got really excited by all the data and insights I was generating and decided to add more and mroe information and go way beyond just the teammates of award winners. I created data sets with all types of ways to evaluate players. I created data bases with stats, data bases with quantiles, and data bases with custom metrics I created, among others. In fact, by adding all this extra data, I uncovered some glitches and other problems and went all the way back to the beginning to address those problems. An example of this is the problem with players moving teams described above. At the beginning, I wanted to look at the past 40 years of each sports and only look at teammates of award winners. My main inquiries will be limited to that context, but I still generated a lot of data.

![eda-mess](images/eda_tch_kag.png)

### Creating relative measures of player performance on a per-season basis.

