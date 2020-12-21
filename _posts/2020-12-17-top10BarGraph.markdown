---
layout: post
title: Which Professions are Most Consistently...?
date: 2020-12-15 13:32:20 +0300
description: Hi, I'm Greer!  You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: post3.jpg # Add image post (optional)
#fig-caption: # Add figcaption (optional)
tags: [Marital Status, Marriage Rates, Occupation, Data Visualization, D3.js]
---
{% include graph3.html %}


## Motivation
Data aggregation/visualization is particularly interesting to me because it tends leads to more questions.  As I was looking at marital trends, I wanted to know which professions are the most likely to be:

* Married, Spouse Present? 
* Married, Spouse absent? 
* Divorced?  
* Separated?
* Widowed?

So, I sought to answer that question.

## Data Aggregation and Graph
I sourced census data from ipums.com.  It contained an individual's occupation (per 1950s codes) and marital status from 1880-2019.  

In python, I loaded the data and built functions that grouped everybody by profession and marital status.  Then I built a few more functions that ranked and sorted the top 10 in each category by percent.  I then built a new pandas data frame with the count of the number of times each occupation was represented in the top ten.  My bar graph used this new data frame and was built in D3.js.

## Issues
I originally used data from 1880-2019 but ran into some interesting issues.  

* “Separated” had a huge bar with no text that described what that bar is.  The issue?  NaNs.  There were 60 NaNs in this column, which didn’t make sense.  So, I went back into python and figured out that “Separated” wasn’t even a marital status category you could claim on the census until 1950.  The data from 1880-2000 was incremented by decade, so 1880-1990 represented 6 years.  Since 6x10=60, there were 60 NaNs in “Separated”.

* I also decided that incrementing by 10 years from 1880-2000 and then by 1 year from 2000-2019 made the numbers skew in favor of later years, so I decided to only use data from 2000-2019.

Now the maximum count is 20.  So, if you see an occupation, like dentistry, that has a count of 20, then you know that that occupation was in the top 10 for its marital status for 20 years.  Which is impressive to say the least.

## Takeaway Questions
* How does age and income come into play with marital status?
* What about Geography?  What do things look like from state to state?
* Are there trends between political party lines too?

## Observations
* Practical nurses in the top 10 for divorce for 20 years straight.
* I understand how members of the military may be away from their spouse but was surprised to find that a farm laborer and roofer were away from their spouse so consistently.
* Dentists, Optometrists, Physicians and Surgeons, Farmers, and Clergymen were in the top 10 for "Married, Spouse Present" for 20 years straight.
* Charwomen and cleaners, Attendants hospital and other institution, and Laundry and dry-cleaning Operatives were in the top 10 for "Separated" for 20 years straight.
* There was a grand total of 12 occupations listed in the top 10 for "Single, Never Married."  Which is wild since other categories reported upwards of 60 occupations over the years.  Which means that these occupations are filled most consistently by single people than in any other category and vary only slightly from year to year.  These jobs also don't necessarily require a college or high school degree, meaning they may be filled by younger people. 
* Widowed was the saddest for me. Demonstrators, people who left this category blank on their census, dressmakers and seamstresses, except factory, Charwomen and cleaners, and Telephone operators were in the top 10 for "Widowed" for 20 years straight. 

## GitHub Code
* Data Source: ipums.com
* Git Repository: https://github.com/ghomer12/Top10MaritalStatusByOCC




