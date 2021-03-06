2011-12 English Premier League Data
===================================

This folder contains summary statistical data and contextual data from every match of the 2011-12 English Premier 
League season.  The summary statistical data is the public dataset of the MCFC Analytics project, and the 
contextual data is the result of the Enriched Data Project that Soccermetrics started in support of MCFC Analytics. 
The full data set populated an early version of the Soccermetrics API, which is a sports modeling and 
analytics layer on top of match data sources.

The data set has been revised in order to be loaded in match databases created with the latest generation of 
Soccermetrics' [Marcotti data schema](https://github.com/soccermetrics/marcotti).  In addition to making data 
available, the goal of the data set is to describe the required files and the expected fields within.  In some of the 
data files, there are `ID` fields that associated with the supplier's internal databases, but those fields are optional.

There are some fields that are not populated yet.  Relative humidity has not yet been filled for all matches, and 
some goal events are marked as "Unknown".  Some booking events are described as "reckless challenge", which may not 
necessarily be an accurate description of the foul.  

The data has been described in the following articles:

* [Introducing the Soccermetrics API](http://www.soccermetrics.net/soccer-database-development/introducing-the-soccermetrics-api)
* [Further comments on the MCFC Analytics Dataset](http://www.soccermetrics.net/match-data-collection/further-comments-on-the-mcfc-analytics-dataset)
* [Introducing the Football Match Result and Summary Database](http://www.soccermetrics.net/soccer-database-development/fmrd-summary-schema-introduction)

The dataset includes the following files:

File Name | Description
----------|-------------
Competitions.csv | Football Competitions
Clubs.csv | Football Club Names
Venues.csv | Match Venues
Players.csv | Biographical Player Data with Default Position
Managers.csv | Biographical Manager Data
Referees.csv | Biographical Referee Data
Matches.csv | High-Level Match Data
MatchLineups.csv | Starting/Bench Players in Matches
Goals.csv | Goal Events in Matches (not including Penalties)
Penalties.csv | Penalty Events
Bookables.csv | Disciplinary Events
Substitutions.csv | Substitution Events
PlayerStats.csv | Summary Statistical Data of all Players

Competitions
------------

Field | Description | Type
------|-------------|------
ID | Supplier ID of competition record | Integer
Name | Name of football competition | String
Level | Level of competition in league pyramid | Integer
Country | Country to which competition belongs | String

Clubs
-----

Field | Description | Type
------|-------------|-----
ID | Supplier ID of club record | Integer
Name | Name of football club | String
Country | Country in which club resides | String

Venues
------

Field | Description | Type
------|-------------|-----
Venue Name | Name of match venue | String
City | City/locality where venue resides | String
Region | Administrative region (state/province equivalent) | String
Country | Country of venue | String
Timezone | Timezone region of venue | String
Altitude | Venue altitude (-200 to 4500 meters) | Decimal
Latitude | Venue latitude (-90.000000 to 90.000000 degrees) | Decimal
Longitude | Venue longitude (-180.000000 to 180.000000 degrees) | Decimal
Config Date | Effective date (YYYY-MM-DD) of venue configuration | String
Surface | Type of playing surface | String
Length | Length of playing surface (90 to 120 meters) | Decimal
Width | Width of playing surface (45 to 90 meters) | Decimal
Capacity | Total venue capacity | Integer
Seats | Total seats at venue | Integer

Players
-------

Field | Description | Type
------|-------------|-----
ID | Supplier ID of player record | Integer
Country | Country of player | String
First Name | Self-explanatory | String
Middle Name | Middle name(s), if applicable | String
Last Name | Primary surname | String
Second Last Name | Second surname, usually the mother's surname | String
Nickname | Popularly known name of player | String
Name Order | Naming Order (NameOrderType) | String
DOB | Birthdate (YYYY-MM-DD) of player | String
Position | Default position of player | String

Managers
--------

Field | Description | Type
------|-------------|-----
Country | Country of manager | String
First Name | Self-explanatory | String
Middle Name | Middle name(s), if applicable | String
Last Name | Primary surname | String
Second Last Name | Second surname, usually the mother's surname | String
Nickname | Popularly known name of manager | String
Name Order | Naming Order (NameOrderType) | String
DOB | Birthdate (YYYY-MM-DD) of manager | String

Referees
--------

Field | Description | Type
------|-------------|-----
Country | Country of referee | String
First Name | Self-explanatory | String
Middle Name | Middle name(s), if applicable | String
Last Name | Primary surname | String
Second Last Name | Second surname, usually the mother's surname | String
Nickname | Popularly known name of referee | String
Name Order | Naming Order (NameOrderType) | String
DOB | Birthdate (YYYY-MM-DD) of referee | String

Matches
-------

Field | Description | Type
------|-------------|-----
Date | Match date | String
Matchday | League matchday | String
Venue | Match venue | String
Home Team | Self-explanatory | String
Away Team | Self-explanatory | String
Home Mgr | Name of home team manager | String
Away Mgr | Name of away team manager | String
Referee | Name of match referee | String 
Attendance | Match attendance |  Integer
1st Half | Length of first period | Integer
2nd Half | Length of second period | Integer
KO Time | Local time (HH:MM) at kickoff | String 
KO Temp | Temperature at kickoff (-15.0 to 50.0 C) | Decimal 
KO Humidity | Relative humidity at kickoff (0.0 to 100.0%) | Decimal 
KO Wx | Predominate weather condition at kickoff (WeatherConditionType) | String
HT Wx | Predominate weather condition at halftime (WeatherConditionType) | String
FT Wx | Predominate weather condition at end of match (WeatherConditionType) | String

MatchLineups
------------

Field | Description | Type
------|-------------|-----
Matchday | League matchday | Integer
Home Team | Self-explanatory | String
Away Team | Self-explanatory | String
Player's Team | Self-explanatory | String 
Player | Full name or nickname of player | String 
Starting | Starting player flag (1=yes, 0=no) | Integer 
Captain | Captain flag (1=yes, 0=no) | Integer

Goals
-----

Field | Description | Type
------|-------------|-----
Matchday | League matchday | Integer
Home Team | Self-explanatory | String
Away Team | Self-explanatory | String
Team | Name of scoring team | String 
Player | Full name or nickname of player | String 
Event | Shot event that resulted in goal (ShotEventType) | String
Bodypart | Body part used to score goal (BodypartType) | String
Time | Match time in minutes (1 to 90 minutes) | Integer
Stoppage | Stoppage time in minutes, if applicable | Integer

Penalties
---------

Field | Description | Type
------|-------------|-----
Matchday | League matchday | Integer
Home Team | Self-explanatory | String
Away Team | Self-explanatory | String
Penalty Taker | Full name or nickname of player taking penalty | String 
Foul | Foul event that resulted in penalty (FoulEventType) | String
Outcome | Outcome of penalty kick (ShotOutcomeType) | String
Time | Match time in minutes (1 to 90 minutes) | Integer
Stoppage | Stoppage time in minutes, if applicable | Integer

Bookables
---------

Field | Description | Type
------|-------------|-----
Matchday | League matchday | Integer
Home Team | Self-explanatory | String
Away Team | Self-explanatory | String
Player | Full name or nickname of player being booked | String 
Foul | Foul event that resulted in penalty (FoulEventType) | String
Card | Disciplinary card shown (CardType) | String
Time | Match time in minutes (1 to 90 minutes) | Integer
Stoppage | Stoppage time in minutes, if applicable | Integer

Substitutions
-------------

Field | Description | Type
------|-------------|-----
Matchday | League matchday | Integer
Home Team | Self-explanatory | String
Away Team | Self-explanatory | String
Player In | Full name or nickname of player substituted into match | String 
Player Out | Full name or nickname of player substituted out of match | String 
Time | Match time in minutes (1 to 90 minutes) | Integer
Stoppage | Stoppage time in minutes, if applicable | Integer

PlayerStats
-----------

Field | Description | Type
------|-------------|-----
Date | Match date (YYYY-MM-DD) | Integer 
Matchday | League matchday | Integer 
Player ID | Supplier ID of player record | Integer
Last Name | Last name of player | String
First Name | First name of player | String
Team | Name of player's team | String
Team Id | Supplier ID of player's team | Integer 
Opposition | Name of opposing team | String 
Opposition Id | Supplier ID of opposing team | Integer
Venue | Locale of match from player's perspective (Home/Away) | String 
Position Id | Supplier ID of player's position | Integer
Assists | Total number of assists | Integer
Goal Assist Corner | Assists directly from a corner kick| Integer
Goal Assist Free Kick | Assists directly from a free kick | Integer
Goal Assist Throw In | Assists directly from a throw-in | Integer
Goal Assist Goal Kick | Assists directly from a goal kick | Integer
Goal Assist Set Piece | Assists directly from a set-piece | Integer   
Total Clearances | Total number of balls cleared from defensive areas | Integer
Headed Clearances | Clearances made with the head | Integer
Other Clearances | Clearances made with feet or body parts other than head | Integer
Clearances Off the Line | Clearances made before ball crossed goal line | Integer
Corners Taken incl short corners | Number of corners taken (including short corners) | Integer
Short Corners | Number of short corners taken | Integer
Successful Corners into Box | Corners into penalty area that found a teammate | Integer
Unsuccessful Corners into Box | Corners into penalty area that did not find a teammate | Integer
Successful Corners Left | Successful corner kicks that started from left side | Integer
Unsuccessful Corners Left | Unsuccessful corner kicks that started from left side | Integer
Successful Corners Right | Successful corner kicks that started from right side | Integer
Unsuccessful Corners Right | Unsuccessful corner kicks that started from right side| Integer
Successful Crosses Corners | Crossing passes from corners that found a teammate | Integer
Unsuccessful Crosses Corners | Crossing passes from corners that did not find a teammate | Integer
Successful Crosses Corners in the air | Successful crosses from corners that traveled through the air | Integer
Unsuccessful Crosses Corners in the air | Unsuccessful crosses from corners that traveled through the air | Integer
Successful Crosses Corners Left | Successful crosses from corners that started from left side | Integer
Unsuccessful Crosses Corners Left | Unsuccessful crosses from corners that started from left side | Integer
Successful Crosses Corners Right | Successful crosses from corners that started from right side | Integer
Unsuccessful Crosses Corners Right | Unsuccessful crosses from corners that started from right side | Integer
Successful crosses in the air | Total crosses through the air that reach teammate | Integer
Unsuccessful crosses in the air | Total crosses through the air that miss teammate | Integer
Successful open play crosses | Total crosses during open play that reach teammate | Integer
Unsuccessful open play crosses | Total crosses during open play that miss teammate | Integer
Successful Crosses Left | Total crosses from left flank that reach teammate | Integer
Unsuccessful Crosses Left | Total crosses from left flank that miss teammate | Integer
Successful Crosses Right | Total crosses from right flank that reach teammate | Integer
Unsuccessful Crosses Right | Total crosses from right flank that miss teammate | Integer
Blocks | Total number of blocked balls | Integer
Interceptions | Total number of pass interceptions | Integer
Recoveries | Number of balls recovered after initial loss of possession | Integer
Corners Conceded | Number of ball touches by player that resulted in corner kick by opposition | Integer
Total Fouls Conceded | Number of fouls committed by player | Integer
Challenge Lost | Number of lost tackles, duels, or other ball challenges | Integer
Handballs Conceded | Number of handball fouls committed by player | Integer
Penalties Conceded | Number of fouls committed by player resulting in penalties | Integer
Error leading to Goal | Number of errant actions that resulted in goal by opposing team | Integer
Error leading to Attempt | Number of errant actions that resulted in shot (no goal) by opposing team | Integer
Yellow Cards | Number of yellow cards received in match | Integer
Red Cards | Number of red or yellow/red cards received in match | Integer
Duels won | Total number of 50/50 balls or tackles won | Integer
Duels lost | Total number of 50/50 balls or tackles lost | Integer
Aerial Duels won | Total number of 50/50 headed balls won | Integer
Aerial Duels lost | Total number of 50/50 headed balls lost | Integer
Ground Duels won | Total number of ground challenges won (dribbles/tackles) | Integer
Ground Duels lost | Total number of ground challenges lost | Integer
Total Fouls Won | Total number of fouls won by a player in match | Integer
Fouls Won in Danger Area inc pens | Total number of fouls won in area close to goal (not penalty) | Integer
Foul Won Penalty | Total number of fouls won that earn a penalty kick | Integer
Fouls Won not in danger area | Total number of fouls won in area far from goal | Integer
Direct Free-kick On Target | Number of direct free kicks that entered the goal face | Integer
Direct Free-kick Off Target | Number of direct free kicks that did not enter the goal face | Integer
Goals Conceded Inside Box | Number of goals conceded that were taken inside penalty area | Integer
Goals Conceded Outside Box | Number of goals conceded that were taken outside penalty area | Integer
Clean Sheets | Clean sheet indicator (i.e. no goal conceded); 0=no, 1=yes | Integer
Saves Made from Inside Box | Number of saved shots that were taken inside penalty area | Integer
Saves Made from Outside Box | Number of saved shots that were taken outside penalty area | Integer
Saves from Penalty | Number of saved penalty shots | Integer
Shots On Conceded Inside Box| Number of shots faced that were taken inside penalty area | Integer
Shots On Conceded Outside Box | Number of shots faced that were taken outside penalty area | Integer
Big Chances Faced | Number of shots allowed that represented a clear goalscoring chance | Integer
Catches | Number of balls caught and held by goalkeeper | Integer
Punches | Number of balls punched away by goalkeeper | Integer
Drops | Number of balls allowed to fall to ground by goalkeeper | Integer
Crosses not Claimed | Number of crosses that were not caught or punched by goalkeeper | Integer
GK Successful Distribution | Number of passes by goalkeeper that are controlled by a teammate | Integer
GK Unsuccessful Distribution | Number of passes by goalkeeper that are not controlled by a teammate | Integer
Headed Goals | Goals scored by header | Integer
Left Foot Goals | Goals scored with left foot | Integer
Right Foot Goals | Goals scored with right foot | Integer
Goals from Inside Box | Goals scored in penalty area | Integer
Goals from Outside Box | Goals scored outside penalty area | Integer
First Goal | Did player score the opening goal? 1=yes, 0=no | Integer
Winning Goal | Did player score the winner? 1=yes, 0=no | Integer
Goals from Direct Free Kick | Goals scored direct from free kick | Integer
Goals Open Play | Goals scored from open play | Integer
Goals from Corners | Goals scored as result of corner | Integer
Goals from Throws | Goals scored as result of throw-in | Integer
Goals from penalties | Goals scored by penalty | Integer
Goals as a substitute | Goals scored as substitute | Integer
Other Goals | Other goals scored | Integer
Shots Cleared off Line Inside Area | Number of shots from inside penalty area that are cleared off goal line | Integer
Shots Cleared off Line Outside Area | Number of shots from outside penalty area that are cleared off goal line | Integer
Shots Cleared off Line | Total number of shots cleared off goal line | Integer
Key Corner | Number of corners taken deemed to have impact in match | Integer
Key Free Kick | Number of free kicks taken deemed to have impact in match | Integer
Key Throw In | Number of throw-ins taken deemed to have impact in match | Integer
Key Goal Kick | Number of goal kicks taken deemed to have impact in match | Integer
Pass Forward | Total passes played toward opponent's goal | Integer
Pass Backward | Total passes played toward own goal | Integer
Pass Left | Total passes played toward left touch line | Integer
Pass Right | Total passes played toward right touch line | Integer
Successful Short Passes | "Short" length passes that reach a teammate | Integer
Unsuccessful Short Passes | "Short" length passes that do not reach a teammate | Integer
Successful Long Passes | "Long" length passes that reach a teammate | Integer
Unsuccessful Long Passes | "Long" length passes that do not reach a teammate | Integer
Successful Flick-Ons | Re-directed passes that reach a teammate | Integer
Unsuccessful Flick-Ons | Re-directed passes that do not reach a teammate  | Integer
Successful Passes Own Half | Passes initiated from own half that reach a teammate | Integer
Unsuccessful Passes Own Half | Passes initiated from own half that do not reach a teammate  | Integer
Successful Passes Opposition Half | Passes initiated from opposition half that reach a teammate | Integer
Unsuccessful Passes Opposition Half | Passes initiated from opposition half that do not reach a teammate | Integer
Successful Passes Defensive third | Passes initiated from defensive third of field that reach a teammate | Integer
Unsuccessful Passes Defensive third | Passes initiated from defensive third of field that do not reach a teammate | Integer
Successful Passes Middle third | Passes initiated from middle third of field that reach a teammate | Integer
Unsuccessful Passes Middle third | Passes initiated from middle third of field that do not reach a teammate | Integer
Successful Passes Final third | Passes initiated from final third of field that reach a teammate | Integer
Unsuccessful Passes Final third | Passes initiated from final third of field that do not reach a teammate | Integer
Total Successful Passes All | All passes that are successfully controlled by a teammate | Integer
Total Unsuccessful Passes All | All passes that are not successfully controlled by a teammate | Integer
Total Successful Passes Excl Crosses Corners | All successful passes, excluding crosses that result from corners | Integer
Total Unsuccessful Passes Excl Crosses Corners | All unsuccessful passes, excluding crosses that result from corners | Integer
Successful Long Balls | All successful long passes (30 meters or more) | Integer
Unsuccessful Long Balls | All unsuccessful long passes | Integer
Successful Lay-Offs | All successful lay-off passes | Integer
Unsuccessful Lay-Offs | All unsuccessful lay-off passes | Integer
Through Ball | All passes between a group of defenders toward a teammate | Integer
Key Passes | All passes deemed important to buildup or team strategy | Integer
Penalties Taken | Number of penalties taken by player | Integer
Penalties Saved | Number of penalties saved by goalkeeper | Integer
Penalties Off Target | Number of penalties put on target | Integer
Attempts from Penalties on target | Number of penalties put off target | Integer
Headed Shots On Target | Number of shots on goal taken with head | Integer
Headed Shots Off Target | Number of shots not on goal taken with head | Integer
Left Foot Shots On Target | Number of shots on goal taken with left foot | Integer
Left Foot Shots Off Target | Number of shots not on goal taken with left foot | Integer
Right Foot Shots On Target | Number of shots on goal taken with right foot | Integer
Right Foot Shots Off Target | Number of shots not on goal taken with right foot | Integer
Blocked Direct Free-kick | Number of direct free kicks blocked | Integer
Blocked Shots from Inside Box | Number of blocked shots that were made inside penalty area | Integer
Blocked Shots Outside Box | Number of blocked shots that were made outside penalty area | Integer
Headed Blocked Shots | Number of blocked shots that were taken with the head | Integer
Left Foot Blocked Shots | Number of blocked shots that were taken with left foot | Integer
Right Foot Blocked Shots | Number of blocked shots that were taken with right foot | Integer
Other Blocked Shots | Number of blocked shots made or taken under other scenarios | Integer
Blocked Shots | Total number of blocked shots | Integer
Shots On from Inside Box | Number of shots on goal taken from inside penalty box | Integer
Shots Off from Inside Box | Number of shots not on goal taken from inside penalty box | Integer
Shots On Target Outside Box | Number of shots on goal taken from outside penalty box | Integer
Shots Off Target Outside Box | Number of shots not on goal taken from outside penalty box | Integer
Attempts Open Play on target | Number of shots from open play that were on goal | Integer
Attempts Open Play off target | Number of shots from open play that were not on goal | Integer
Attempts from Set Play on target | Number of shots from set plays that were on goal | Integer
Attempts from Set Play off target | Number of shots from set plays that were not on goal | Integer
Attempts from Direct Free Kick on target | Number of shots from direct free kicks that were on goal | Integer
Attempts from Direct Free Kick off target | Number of shots from direct free kicks that were not on goal | Integer
Attempts from Corners on target | Number of shots from corner kicks that were on goal | Integer
Attempts from Corners off target | Number of shots from corner kicks that were not on goal | Integer
Attempts from Throws on target | Number of shots from throw-ins that were on goal | Integer
Attempts from Throws off target | Number of shots from throw-ins that were not on goal | Integer
Other Shots On Target | Number of miscellaneous shots that were on goal | Integer
Other Shots Off Target | Number of miscellaneous shots that were not on goal | Integer
Shots On Target inc goals | Number of shots made into goal face, including successful shots | Integer
Shots Off Target inc woodwork | Number of shots made that flew away/over goal face or hit posts | Integer
Big Chances | Number of shots that represented clear chances to score | Integer
Tackles Won | Number of successful tackles attempts by player | Integer
Tackles Lost | Number of unsuccessful tackle attempts | Integer
Last Man Tackle | Number of successful last-man tackles | Integer
Throw Ins to Own Player | Number of throw-ins controlled by a teammate | Integer
Throw Ins to Opposition Player | Number of throw-ins controlled by an opposing player | Integer
Take-Ons Overrun | Number of dribbling attempts where ball rolls away | Integer
Successful Dribbles | Number of successful dribbles/take-ons past opponent | Integer
Unsuccessful Dribbles | Number of unsuccessful dribbles/take-ons past opponent | Integer
Successful Ball Touch | Number of successful ball touches (controlled possession) | Integer
Unsuccessful Ball Touch | Number of unsuccessful ball touches (lost possession) | Integer
Dispossessed | Number of lost possessions | Integer
Touches | Total number of ball touches | Integer
Touches open play final third | Number of touches in opposing final third of pitch | Integer
Touches open play opp box | Number of touches within opposing penalty area | Integer
Touches open play opp six yards | Number of touches within opposing goal (six-yard) area | Integer

Sources:

* FA Premier League
* Press reports
* Weather Underground
* Opta Sports