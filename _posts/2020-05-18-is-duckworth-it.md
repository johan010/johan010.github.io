# Is duckworth Lewis worth it?

This project was created because I was curious as to how accurate duckworth lewis stern (DLS) actually is (mostly due to South Africa getting the short end of this stick a couple of times). The project link can be found [here](https://github.com/johan010/is-duckworth-it)

I started off trying to do this using cricinfo's Statsguru, but maybe I didn't know how, but it did not seem possible to do so. So I created this project with the following aim:

_calculate the accuracy of DLS at different point of a chasing ODI innings. To do this I would need to get ball by ball data, process that data into useable format, calculate DLS at different points of the 2nd innings of each match, see if the current total is bigger or smaller than the DLS par score, compare that to the team that actually won the match and finally see how often DLS got it right._

# Getting the data
I realised that cricinfo is stingy with providing ball by ball data, so I found cricsheet. They provide ball by ball match data in .yaml format, which is exactly what I needed. So I fetched all the matches and saved it in a local directory. My project repo readme provides instructions for anyone that wants to do the same. The data inlcudes smaller nations ODI's like Nepal.

# Processing the data
To get the data into a useable format, I had to do a lot of processing. I processed the .yaml files into one large dataframe, after which I could do some calculations. For each ball in the 2nd innings I then calculated the DLS par score and compared that to the actual 1st innings total, after which I could group all the data together into each over of the 2nd innings, where I counted the number of times the dls was correct and divided that by the total number of instaces to get the accuracy.

# results
In the end the data contained a total of 1722 male ODI's with the earliest match being start of 2004. Only matches where there were no overs missed in the game was considered to avoid complicating the DLS calculations. The results can be seen in the following graph:
##insert graph here

The DLS accuracy increases steadily as the number of overs bowled increases. This demonstrates also why DLS is only used when a minimum of 20 overs has been bowled, to avoid the decreased accuracy at the start of the innings. Towards the end of the innings the accuracy approaches 90%. It would be interesting to see whether the accuracy of DLS changes when the team is aware of the DLS target and there is a threat of rain. Obviously this is difficult to get from this data and would probably require manually checking where this happened.


