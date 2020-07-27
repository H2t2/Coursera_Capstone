# Coursera Capstone

A repo for my Capstone Project for IBM's Data Science Certificate


## Introduction

Everyone has that beloved special food spot. Whether it’s a small burger joint, or a large family restaurant with the best mashed potatoes. We each have a special restaurant that fondly warms our belly.  

The question is, which city in Orange County has the most of these wonderfully delicious places?

Through a combination of a Geographical Data, FourSquare’s API, and machine learning algorithms, I will find which communities have the highest rated restaurants, segementing Orange County in the groups based on how delicious the food is. 

## Data

I plan to use FourSquare's Places API, along with geographical data to tackle this problem. Using geographical data, like the coordinates of city centers and size of each city, I will build areas in which to search. I will utilize FourSquare’s Places API to search within those areas and build a list of restaurants and ratings.

In order to draw data from FourSquare's API, a developer account must be set up. Credentials are needed for every request to FourSquare's API. I have hidden those credentials in Environment Variables, located in an .env file.

### What kind of data?

The most simple approach would be to generate a data set of the top 100 restaurants in each city, average the ratings and compare the results. That will be my first exploratory step. While quick, I don't believe this method will generate quality insight, because there are notable demographic differences across municipalities in Orange County, such a as size, average income, racial makeup, and population. 

The first step is to generate a list of all cities in Orange County. The list can be found here: https://media.ocgov.com/about/infooc/links/oc/occities.asp. Pulling the list of cities out of the html can be done by hand, or with Python Library Beautiful Soup


