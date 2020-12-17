---
layout: post
title: Which Professions are Most Consistently...?
date: 2020-12-15 13:32:20 +0300
description: Hi, I'm Greer!  You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: post3.jpg # Add image post (optional)
#fig-caption: # Add figcaption (optional)
tags: [Holidays, Hawaii]
---
{% include graph3.html %}


## Motivation
Data aggregation/visualization is interesting because it usually leads to more and more questions.  As I was looking at marital trends, I wanted to know which professions are the most likely to be:

* Married with heir spouse present? 
* Married with heir spouse absent? 
* Divorced?  
* Separated?
* Widowed?

So, I sought to answer that question.

## The Graph
In python, I loaded the data and used some functions that I had already built that grouped everybody from the census data I pulled from ipums.com by profession and marital status.  Then I built a few more functions that ranked and sorted the top 10 in each category by percent.  I then built a new data frame with the count of the number of times each occupation was represented in the top ten.  My bar graph was built in D3.js.

I originally used data from 1880-2019, but I ran into some interesting issues.  

* “Separated” had a huge bar with no text that described what that bar is.  The issue?  NANs.  There were 60 nans in this column, which didn’t make sense.  So I went back into python and figured out that “Separated” wasn’t even a category you could claim for marital status until 1950.  The data from 1880-2000 was incremented by decade, so 1880-1990 represented 6 years.  Since 6x10=60, there were 60 NaNs in “Separated”.

* I also decided that incrementing by 10 years from 1880-2000 and then by 1 year from 2000-2019 made the numbers skew in favor of later years, so I decided to only use data from 2000-2019.

So now the maximum count is 20.  So if you see an occupation, like denistry, that has a count of 20, then you know that that occupation was in the top 10 for it's marital status for 20 years.  Which, is impressive to say the least.

## Takeaway Questions
* How does age and income come into play with marital status?
* What about Geography?  What do things look like from state to state?
* Are there trends between political party lines too?

## Observations
* Why were practical nurses in the top 10 for divorce for 20 years straight?
* I understand how members of the military may be away from their spouse, but why would a farm laborer or roofer be away from their spouse so consistently?
* Dentists, Optomitrists, Physicians and Surgeons, Farmers, and Clergymen were in the top 10 for "Married, Spouse Present" for 20 years straight.
* Charwomen and cleaners, Attendants hospital and other institution, and Laundry and dry cleaning Operatives were in the top 10 for "Separated" for 20 years straight.
* There were a grand total of 12 occupations listed in the top 10 for "Single, Never Maried."  Which is  wild since other categories reported upwards of 60 occupations.  Which means that these occupations are the most single and vary only slightly.  They also seem to be jobs that that don't necessarily require a college or high school degree, meaning they may be younger people. 
* Widowed was the saddest for me. Demonstrators, People who left this category blank on their census, Dressmakers and seamstresses, except factory, Charwomen and cleaners, and Telephone operators were in the top 10 for "Widowed" for 20 years straight. 

## Github Code
* Data Source: ipums.com
* Git Repository: https://github.com/ghomer12/Top10MaritalStatusByOCC



