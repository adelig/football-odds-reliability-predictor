# Football Odds - Reliability Predictor
![alt text](https://img.shields.io/badge/License-GPL%20v3-blue.svg)
![alt text](https://img.shields.io/badge/Python-3.5-blue.svg)
![alt text](https://img.shields.io/versioneye/d/ruby/rails.svg) <br />

Find out the most trustworthy football game out of all the scheduled English Premier League matches for tomorrow. <br />
<br />
Initially, fetch all the historical [betting odds data](http://football-data.co.uk/englandm.php) from season 2000/2001 onwards - every time the code executes it fetches the most updated data for the current season - and compute the average odds value (among all the available betting companies) for each particular match played for the three potential results Home/Draw/Away separately. <br />
<br />
Then, scrape the [William Hill bookmaker page](http://sports.williamhill.com/bet/en-gb/betting/y/5/tm/1/Football.html) and bring the list of all the scheduled English Premier League tomorrow's matches along with their offered odds for each potential outcome Home/Draw/Away. <br />
<br />
For each one of the upcoming matches, filter out the initial database accordingly in order to keep only the given pair of teams over the years (and the respective odds). So, given the exact date of each game, and representing each of the three outcomes Home/Draw/Away as value y, can predict the next value of each of the three possible results as a time series next step. This is done utilizing the famous [Facebook's Prophet forecasting algorithm](https://github.com/facebook/prophet) which is robust to missing data, shifts in the trend, and large outliers. <br />
<br />
Compute the sum of the distances between the three results among the offered and the predicted values for each one of the listed matches and pick the one with the minimum sum of distances. This is considered as the most reliable game to potentially bet on.
