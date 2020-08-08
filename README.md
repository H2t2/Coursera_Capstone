# Coursera Capstone

A repo for my Capstone Project for IBM's Data Science Certificate


## Introduction

Everyone has that beloved special food spot. Whether it’s a small burger joint, or a large family restaurant with the best mashed potatoes. We each have a special restaurant that fondly warms our belly.  

The question is, which city in Orange County has the most of these wonderfully delicious places?

Utilizing FourSquare’s API, and machine learning algorithms, I will find which communities have the highest rated restaurants, and performing analysis on data.

## Data

I plan to use FourSquare's Places API to tackle this problem, and perform exploratory analysis on the data. 

### What kind of data?

The most simple approach would be to generate a data set of the top restaurants in each city, average the ratings and compare the results. That will be my first exploratory step. 

The first step is to generate a list of all cities in Orange County. The list can be found here: https://media.ocgov.com/about/infooc/links/oc/occities.asp. Pulling the list of cities out of the html can be done by hand, or with the Python Library Beautiful Soup.

### Issue with Foursquare's Places API, switching to Yelp's Fusion API
#### The Grass is Greener in the other API
A problem with Fourquare's API is that each call is limited to 50 results. The limited result set and the inablilty to strictly search within a city causes a bleeding problem, where results from other cities pollute the result set. An apparent solution would be to utilize the parameters in the API call to limit the search around a certain radius. However, since cities in Orange County are rarely uniform, it is difficult to encapsulate the target city within a radius without capturing pollution from adjacent locals. Even within a relatively small City like Aliso Veijo, the pollution is so bad that only 4 results of the 50 are located in Aliso Veijo.

I chose to switch from Foursquare's API to Yelp's API, which has the ability "page" through the result set of 1000. Although Yelp's implementation is much like Foursquare's, using a search radius and having no way to strictly filter by city, I feel using Yelp is the better option. If the results mirror Foursqaure's by ratio, we would expect about 80 results located in Aliso Veijo, which allows a more level population of desired data across cities.

The lingering problem with search radius can also be addressed by utilizing the API's sort_by parameter. Allowing the result set to be sorted by distance from city centers. The results can be offset or "paginated" until no more target city food locations remain.