# Coursera Capstone

A repo for my Capstone Project for IBM's Data Science Certificate


## Introduction

Everyone has that beloved special food spot. Whether it’s a small burger joint, or a large family restaurant with the best mashed potatoes. We each have a special restaurant that fondly warms our belly.  

The question is, which city in Orange County has the most of these wonderfully delicious places?

Utilizing FourSquare’s API, and machine learning algorithms, I will find which communities have the highest rated restaurants, and performing analysis on data.

## Data

I plan to use FourSquare's Places API to tackle this problem, and perform exploratory analysis on the data. 

### What kind of data?

The most simple approach would be to generate a data set of the top 100 restaurants in each city, average the ratings and compare the results. That will be my first exploratory step. 

The first step is to generate a list of all cities in Orange County. The list can be found here: https://media.ocgov.com/about/infooc/links/oc/occities.asp. Pulling the list of cities out of the html can be done by hand, or with the Python Library Beautiful Soup.

