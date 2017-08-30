I put together some analysis on data from the Autumn Internationals (AIs) down the years. Initially I started out wanting to test my ability to build a web scraper, but I found [Pick and Go](http://www.lassen.co.nz/pickandgo.php) had done a lot of the heavy lifing for me. You can search for matches by date, team, competition. It outputs a nice tabular form that I simply copied to a text file and fed into a Jupyter notebook so I could mess around with the data in Python. 

The initial data had the: 
* *date* the match occured.
* what *tournament* it was associated with. Obviously all were AIs but some also played for other tropies, such as Eng v Aus labeled with "CC" for Cook Cup.
* *round*, this was mostly not populated, except in cases where teams played each other more than once in the Autumn (e.g. Ireland - NZ in 2016), so I didn't give it much attention.
* *match*, e.g ENG v AUS
* *score*, e.g. 37-21
* *tries* for both sides, e.g. 4:2
* *points*, assuming a 4 points for a win, 1 for a four try bonus, 1 for losing within 7 system, e.g. 5-0. Didn't look at this much to be honest.
* *venue*, again I didn't pay this much attention.
* *neutral* venue indicator. Since there was only 5 games marked as being at neutral venues I again didn't focus on this. 

From these initial fields I did some basic data cleaning to create additional fields for easier analysis. Simply extracting the home team, away team, home score, away score, home tries, away tries into separate fields. As well as creating a boolean (true/false) field to indicate a home win, a field to indicate the winning team and one last field to indicate the margin of victory. Even with this basic cleaning we can gain see some nice trends. 

**Number of games** 

INSERT MATCHES PER YEAR

Firstly I had a look at the number of games a year. We have a general upward trend indicated by the red line as clearly more rugby is always better. Also visible is the four year World Cup (WC) cycle where the number of AIs is significantly reduced the years WCs take place. The only exception is 1995, I guess this is because the WC was finished in June of that year? 

**Overall Results**

INSERT PIE CHART

The chart above shows that the home team wins the majority of the time, but it's close. Also, draws are very rare having only  occured 9 times since the inception of AIs. 

Overall the team that scores the most tries wins 75.3 % of the time, and the team scoring fewer tries only winnng 6.7 % of the time. The rest are the  draws (2.3 %) and games where the teams had equal numbers of tries (15.7%) 

**Margin of Victory**

INSERT MARGIN CHART

This shows a fairly skewed distribution with a median winning margin of 14 points. Interestingly if only home wins are taken into account this median increases to 16 points, while only away wins has a median of 11 points. Indicating that the games are closer  when the away team wins (this plot is in the notebook for those interested).

As you can see the highest margin of victory is when England beat Romania by 134-0 in 2001...ouch. Similarly 2004 Japan shipped heavy losses to both Wales and Scotland, 98-0 and 100-8 respectively. 

**Teams Winning Percentage**

INSERT WIN_PERC CHART

Unsurprisingly New Zealand top the list with a win percentage of 84.21%; only 3 teams have managed to beat New Zealand in the Autumn, France and England (4 times each) and Ireland (their 1 and only win against them in 2016). There have been 3 draws involving the All Blacks, against France and England and once against Scotland way back in 1983. New Zealand lead the pack from South Africa (63.93%) before we have a very tight grouping of three teams; England (61.76%), Ireland (61.40%) and Australia (61.25%). I quite like that Ireland are fourth, but feel compelled to point out that Australia have actually played almost 1.5 times as many games as Ireland in AIs. In fact Australia have played the most AIs with 80 and actually have the second highest number of wins with 49. 

Another anomaly to point out is the fact that Portugal (50.00%) sit above both Scotland (43.86%), and Wales (42.46%) by the virtue of having played only 2 games and won 1. So below is the same data orded by number of games won instead of winning percentage. This time our top three are New Zealand, Australia, and France. 

INSERT WIN_GAMES CHART 

**Focussing on this years matches for the Home Nations**

We have some interesting matchups this year, I chose to highlight a few of the tier 1 match ups for the home nations. This was due to a combination of knowing the home nations best, and being too lazy to do much more than that :D. 

*Ireland vs South Africa* 

This should be a doozy, SA on the up and have just leapfrogged Ireland in the rankings, and the stats say this is the most even of the AIs that I had a deeper look into. The teams are tied on 4 wins a piece and the majority have finished at or within the overall AI median of 14 points, the only exception being Ireland's 32-15 victory in 2006.

*Ireland vs Argentina*

Stats tell of a dominant Ireland here, having won all 7 games played between the teams in AIs, with an average winning margin of appoximately 12 points. If only this was true of WC games... Additionally the teams havent met in AIs since 2012, so perhaps the tables will turn with the Rugby Championship experience Argentina have racked up. 

*England vs Argentina* 

England lead the head to head 6-1. The only blot on the record is an 18-25 loss in 2011. Interestly this was one of of the 6.7 % of matches where the winning team scored the fewer tries. 

*England vs Australia*

A rich history to look at here with 17 AIs played; England winning 10, Australia 6 and there has been one draw. England are also on a bit of a roll having won the last 3 AIs...and that isn't even mentioning the summer tour last year. Surely the Aussies will be out for revenge? 

*Wales vs Australia*

Australia clearly in command here having won 11 of the 15 meatings, Wales triumphing 3 times, with one draw. The Welsh wins tended to be tighter affairs having won by 3, 2, and 5 points compared to Australias's average margin of 11. 

*Wales vs South Africa*

South Africa have a commanding lead of 10-2 in the head to head, averaging a winning margin of 10 points. However, the last two wins have been to Wales, can they keep this going? 

*Wales vs New Zealand*

New Zealand who have a streak to rival the Undertaker's at 13-0. The average winning margin is 20 points. However, New Zealand steamroll most teams and their overall average margin against all comers is 22 points. 

*Scotland vs New Zealand*

New Zealand are also undefeated against Scotland in the AIs with an average winning margin 26 points. However, as mentioned above, there has been 1 draw between the sides; 25-25 in 1983.

*Scotland vs Australia*

Scotland won the first meeting back in 1981, but have only won once since; a narrow 1 point win in 2009 giving Australia a 10-2 lead in the head to head. The last few games have been closely fought, after Scotland's victory in 2009, Australia took a 6 point win in 2013 and also had a 1 point win last year. With Scotland's win down under in the summer I'm sure the Scots will be hopeful to get their 3rd victory in this head to head. 

Overall I hope that was interesting, my next steps would be to:
* Do some nicer visualisations, something like and infographic. I have downloaded [tableau](https://www.tableau.com/) to mess around with but I am still figuring it out. 
* Do similar analysis for other competitions, and probably actually get around to build that webscraper for it. 

The full Jupyter notebook, for those interested can be found [here](http://nbviewer.jupyter.org/github/gpmurphy7/Rugby_analysis/blob/master/Autumn_International_Analysis/Autum_Internationals_First_Look.ipynb). 