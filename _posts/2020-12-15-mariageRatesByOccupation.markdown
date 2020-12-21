---
layout: post
title: How do martial status rates by occupation compare to national martial status rates?
date: 2020-12-15 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: mariageRates.jpg # Add image post (optional)
#fig-caption: # Add figcaption (optional)
tags: [Holidays, Hawaii]
---
{% include graph1.html %}


## Motivation
Have you ever wondered what the marriage trends in your profession look like?  I did. While teaching math in my 20s, I noticed that I was one of only a few unmarried educators at my school.  

Most of the teachers I worked with were:
* Women
* Married
* White

By pure observation, it seemed like teachers tended to be married at a higher rate than people who chose other professions, but I wanted to check it out to see what was actually going on.  After taking a Data Visualization course at Georgia Tech (shoutout to Dr. Polo and his intensely interesting cse6242 course), I thought it would be interesting to use what I learned about visualizing data to test this theory.  As it turns out, teachers don't even make the top 10 for most likely to be married.  I plan on posting more on that in the future, but for now I decided to visualize what has happened across all reported professions in America in terms of marital status from 1880-2019.

## Side Note
While aggregating this data in python and visualizing it using seaborn, my mom called. When she asked what I was working on, I told her that I was visualizing marriage rates by occupation per United States census data. Her immediate reaction? "Show me the accountants."  My dad is a retired accountant, so she was naturally curious.  We both got a kick out of how the occupation code as "000" out of the 283 codes listed. I guess that goes to show just how important accounting/money is to Americans!

## About the Data and Graph

The lighter, dotted lines represent the national average by category.  When you choose a profession from the dropdown, solid thicker lines appear that represent the marital status rates by that profession.  I kept the national rates so that whoever uses this visualization can compare the national rates to the selected occupation rates.  I found it particularly interesting how certain status categories seemed to "appear" in the 1950s.

I used ipums.com to pull census data that spanned from 1880 to 2019 and is based on the 1950s Occupational codes. I cleaned and aggregated the data in python and coded my graph in d3.js.  Data visualization is a great tool that allows you to both tell a story and ask better questions.  This is just a starting-off point for a larger conversation I'd like to have on this website, although marriage rates are just one topic that I intend to explore.

## GitHub Code
* Data Source: ipums.com
* Git Repository: https://github.com/ghomer12/MariageRates





