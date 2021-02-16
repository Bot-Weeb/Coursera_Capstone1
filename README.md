# Coursera_Capstone
Business opportunity in Toronto


# **Introduction**

Toronto is a bustling city, with many different types of people living there. It is multicultural, yet certain establishments pop up frequently despite cultural differences. This project groups all the different boroughs of Toronto into various clusters so we can categorize them and draw insight to the current establishments as well as finding oppurtunity for new ones. 

Note: All sources referenced that aren't used in the creation of a dataset will be at the bottom as they help provide context and additional information to help further decisions that the merged datasets will lead us towards.

# Business Potential

The problem is to find a spot in one of Toronto's many boroughs that a certain business can thrive in. We can determine this from popularity in other similar boroughs where certain establishments are very prevelant. The result of the findings could allow for an entrepanuer to take informed measures to sucessfully start and operate a business long term, providing even more growth and value to the area.

# Data Description

Geographical data is mandatory for all of Toronto. Postal codes will help find neighbourhoods, boroughs, and venues as a good starting point.

The starting point is to scrape data. For this project we utilized "https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M" as it had postal codes, boroughs, and neighbourhoods. 

To learn about venues we utilize the Foursquare API as it is a great free api for developers.


##Foursquare API##

Foursquare has call functions that let you learn about different venues and their locations. Theese call functions include latitude, longitude, venue names, and venue categories.

We use the data from foursquare and create a merged dataset from foursquare's information and the scraped wikipedia info to create our default dataset.


Note: It is important to specify a radius. 600m was chosen as it is a little under .4 miles and almost 30 percent of Toronto's adult population (55% in some downtown areas), don't own a motorized vechicle. At 4/10 of a mile your looking at a quick bike or drive and under a 10 minute walk, making it reasonable for that part of the population. This can however be adjusted to be bigger if it is near a public transport area 600m simply lets us examine more neighbourhoods for business oppurtunity.



# Methodology
We will be creating our model with Python. The following packages are utilized.
![github-small](https://github.com/Bot-Weeb/Coursera_Capstone1/blob/main/assets/Required%20libraries.JPG)
Pandas: Collecting and manipulating data from HTML and JSON

sklearn: machine learning model we are utilizing

folium: generates the map of Toronto

matplotlib: details on the generated map

requests: works with http requests

# Data Collection

We begin with collecting the required data for toronto. We need to start by scrapeing our pages to create a complete merged datset.
![github-small](https://github.com/Bot-Weeb/Coursera_Capstone1/blob/main/assets/Part%201%20of%20Merged%20dataset.JPG)

![github-small](https://github.com/Bot-Weeb/Coursera_Capstone1/blob/main/assets/part%202%20of%20merged%20dataset.JPG)

We cleaned the dataset so that way there are no missing or duplicated values and the result is as follows.
![github-small](https://github.com/Bot-Weeb/Coursera_Capstone1/blob/main/assets/merged%20dataset%20result.JPG)

We utilize the foursquare API using client ID and then get nearby venues. Because we are using lattitude and longitude to show off venues we know that there will be 0 duplicates.

![github-medium](https://github.com/Bot-Weeb/Coursera_Capstone1/blob/main/assets/nearby%20venues.JPG)

After that is done we start onehot encoding to convert types of venues to percentages. Follow that up by grouping by neighbourhood and create the following table.
![github-small](https://github.com/Bot-Weeb/Coursera_Capstone1/blob/main/assets/top%2010.JPG)

# Visualization

The map below is a folium map that is the result of k-means clustering applied to the merged dataset shown in the data collection portion.

(If interested in seeing all code line by line there will be an ipynb file on full steps taken to achieve this and everything in data collections.)
![github-medium](https://github.com/Bot-Weeb/Coursera_Capstone1/blob/main/assets/map.JPG)

# Location, Business Understanding, and Results

The aim of the project is to find the best borough/neighbourhood of Toronto to open a restaurant. Toronto is known for good public transport system as such we should aim for a spot close to that and/or big business sectors that also like to be food dense areas. For theese reasons we can narrow down some of the cluster points as they are not close enough to public transport or heavy business/school areas to be as profitable as other areas. We utilize python libraries, web scrapeing, open public data, Foursquare API, and talking with residents to get ideas of what individuals in the area feel is missing.   

If we look at the red dots (cluster 1) it is the large majority of the area and as such is likely to be the most reliable market data.
The 2 most common shops in Cluster 1 are coffee shops, and cafes. Competition will be fierce and should likely be avoided because of it. With the exception of a few parks and gyms, restauraunts of different varieties make up almost all of the top 10 spots. Fast food ranks highly as does fried chicken. From here I could tell a stakeholder that most restaurant venues (provided that they are available by public transport, have good food, etc) can and liekly will be sucessful. However there are 2 places that stand out as being better than the rest.

In between Garden District, Ryerson and Central Bay Street is a popular road near a university and several major hospitals. As such this is an incredibly busy area with heavy traffic. It lacks a strong chicken place so something like a Chic-Fila I think would be a smart move, especially after the opening of Toronto's 1st Chic-Fila has been successfull. Other chicken places could also do well here so long as they can get food out to customers quickly.

The longer term play that I like more however is between Davisville and north Davisville by Eglinton. Toronto is currently building a new major public transport line that plans to finish in about 3 years. Eglinton is fairly high traffic already and becoming a major public transport point would make it a great place to have fast food around. The only real competition I see is a single KFC nearby. This leads me to believe it is another great spot for a Chic-Fila. This spot has a bit of fast food available already but with major public transport coming to the area, the demand for quickly available food will only go up and chicken is among the more popular. Healthier foods also would seem to be more popular in the area and Chic-Fila while not "health food" is pretty healthy especially compared to other fast food places.

# Conclusion

This analysis is performed on a small set of data. Better results can be achieved by increasing total information on the neighbourhoods. Toronto has many differnt people from many different cultures. Despite the many differnt cultures haveing a wide variety of interests everybody needs to eat and we have seen that restauraunts in particular are popular esatblishments. If you are a stakeholder or an individual interested in opening a restauraunt or other venue, the data that was procured and cleaned should help influence your decession. Ultimately thanks to K-means clustering and takeing a look at other restauraunts i think we found 2 awesome spots to open Chic-Fila's.

# Furthering the Project/Future Developments

Consider the following:
1.   Use google maps to have a google based API. The sample size that was worked on was quite small and can have innacuracies because of the size. Google API is simply used in so much more of a widespread manor. Foursquare was a requiremnet for the project however I feel the data suffered due to this requirement(which i attempted to make up for by talking with residents and including other sources)
2.   Reclustering either a different method or messing with the current variables. 

# References

Listed below are all sources I used to influence my decession making that weren't directly used in the data set.



*   https://trreb.ca/files/market-stats/commercial-reports/cw20Q3.pdf
*   http://dmg.utoronto.ca/pdf/tts/2016/2016TTS_Summaries_Toronto_Wards.pdf
*   https://www.toronto.ca/city-government/accountability-operations-customer-service/city-administration/city-managers-office/key-initiatives/transit-in-toronto/transit-expansion/eglinton-east-lrt/
*   Individuals from/currently living in the city
