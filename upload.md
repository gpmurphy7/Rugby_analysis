I did some analysis on data from the Autumn Internationals (AIs) down the years. Initially I started out wanting to test my ability to build a web scraper, but I found [Pick and Go](http://www.lassen.co.nz/pickandgo.php) had done a lot of the heavy lifing for me. You can search for matches by date, team, competition. It outputs a nice tabular form that I simply copied to a text file and fed into a Jupyter notebook so I could mess around with the data in Python. 

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

**Margin of Victory**

INSERT MARGIN CHART

This shows a fairly skewed distribution with the median winning margin of 14 points. Interestingly if only home wins are taken into account this median increases to 16 points, while only away wins has a median of 11 points. Indicating that when the away team wins the game is generally closer (see the notebook for this plot) 

As you can see the highest margin of victory is when England beat Romania by 134-0 in 2001...ouch. Similarly 2004 Japan shipped heavy losses to both Wales and Scotland, 98-0 and 100-8 respectively. 

**Does Scoring More Tries Win games**

Yes, mostly. The team that scores the most tries wins 75.3 % of the time, and the team scoring fewer tries only winnng 6.7 % of the time. The rest are draws (2.3 %) and games where the teams had equal numbers of tries (15.7%) 

**Teams Winning Percentage**

INSERT WIN_PERC CHART

Unsurprisingly New Zealand top the list with a win percentage of 84.21%, leading from South Africa (63.93%) before we have a very tight grouping of three teams; England (61.76%), Ireland (61.40%) and Australia (61.25%). I quite like that Ireland are fourth, but feel compelled to point out that Australia have actually played almost 1.5 times as many games as Ireland in AIs. In fact Australia have played the most AIs with 80 and actually have the second highest number of wins with 49. 

Another anomaly to point out is the fact that Portugal (50.00%) sit above both Scotland (43.86%), and Wales (42.46%) by the virtue of having played 2 won 1. So below is the same dated orded by number of games won instead of winning percentage. This time our top three are New Zealand, Australia, and France. 

INSERT WIN_GAMES CHART 

**Focussing on this years matches for the Home Nations**

We have some interesting matchups this year, I chose to highlight a few of the tier 1 match ups for the home nations. This was due to a combination of knowing the home nations best, and being too lazy to do much more than that :D. 

*Ireland vs South Africa* 

This should be a doozy, SA on the up and have just leapfrogged Ireland in the rankings, and the stats say this is the most even of the AIs between the tier 1 teams. Tied on 4 wins a piece and the majority have finished at or within the overall AI median of 14 points, the only exception being Ireland's 32-15 victory in 2006.

*Ireland vs Argentina*

Stats tell of a dominant Ireland here, having won all 7 games played between the teams in AIs, with an average winning margin of appoximately 12 points. If only this was through of WC games... Additionally the teams havent met in AIs since 2012, so perhaps the tables will turn with the Rugby Championship experience Argentina have racked up. 

*England vs Argentina* 

England lead the head to head 6-1. The only blot on the record is an 18-25 loss in 2011. Interestly this was one of of the 6.7 % of matches where the winning team scored the fewer tries. 

*England vs Australia*

A rich history to look at here with 17 AIs played; England winning 10, Australia 6 and there has been one draw. England are also on a bit of a roll having won the last 3 AIs...and that isn't even mentioning the summer tour last year. Surely the Aussies will be out for revenge? 




The full Jupyter notebook, for those interested can be found add link 