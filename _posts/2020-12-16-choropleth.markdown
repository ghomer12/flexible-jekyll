---
layout: post
title: Who Teaches in America?
date: 2020-12-15 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: choropleth.jpg # Add image post (optional)
#fig-caption: # Add figcaption (optional)
tags: [Holidays, Hawaii]
---
{% include graph2.html %}

## Motivation
It's important that young people see themselves in authority figures. Unfortunately, American teachers are not as diverse as the populations that they serve.  I visualized the racial breakdown of America's educator's state to state.  

## The Graph
I built the choropleth using D3.js, HTML, and CSS after cleaning the csv file in python.  The color scale is based on the number of teachers per state.  The darker colors represent more teachers, the lighter colors represent that there are fewer teachers in that state, and the grey states represent states that did not have any data from my data source.  When you hover your mouse over each state, a bar graph shows the demographic breakdown of teachers in that state.  

## Takeaway Questions
* Why is teaching so heavily white?  
* Why is teaching so attractive to white people?  
* How can we as a nation take strides to attract a population of educators that better represent the students that they teach?

## Observations
* The states with fewer teachers tend to have a higher percentage of white teachers.  
* Texas has the greatest number of teachers and the greatest teacher diversity nation-wide.

## GitHub Code
* Data Source: https://nces.ed.gov/surveys/sass/tables/sass1112_2013314_t1s_001.asp
* Git Repository: https://github.com/ghomer12/D3_TeacherChoropleth1





