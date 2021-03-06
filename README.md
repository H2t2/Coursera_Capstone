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
While brainstorming and planning the next steps in the data gathering process, I realized the complexity of using Foursquares API to mine the desired information. As Yelp has become a large leader in the same space, I chose to use Yelp.

#### The Grass is Greener in the other API
A problem with Fourquare's API is that each call is limited to 50 results. The limited result set becomes a more prominent issue with another constraint of Foursquare's API. There is no way to strictly search within a city. The inability to strict search causes a bleeding problem, where results from other cities pollute the result set. An apparent solution would be to utilize the parameters in the API call to limit the search around a certain radius. However, cities in Orange County are rarely uniform, so it is difficult to encapsulate the target city within a radius without capturing pollution from adjacent locals. Even within a relatively small City like Aliso Veijo, the pollution is so bad that only half of the results are located in Aliso Veijo.

Yelp's API has the ability "page" through the a larger result set of 1000 and also introduces result set sorting. Yelp's implementation is like Foursquare's, they use a search radius and have no way filter by city. Even so, I feel using Yelp is the better option, because a larger result set will allow building a more robust data set. The problem with search radius can also be addressed by utilizing the API's sort_by parameter. Allowing the result set to be sorted by distance from city centers. The results can be offset or "paginated" until no more target city food locations remain.

Finally, Foursquare's search API does not have ratings data, and would require a seperate process to individually call the API for each restaurant in the data set (perhaps a programming project for another day). The larger dataset from Yelp, along with automatically included rating data, and sort functionality, simplifies the choice to use Yelp's API instead.

####