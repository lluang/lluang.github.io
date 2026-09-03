---
title: "Data Manipulation with R by Spector: Book Review"
date: 2015-07-09
permalink: /posts/2015/07/data-manipulation-with-r-by-spector/
tags:
  - "book review"
  - "data science"
  - "math"
  - "programming"
  - "R-Project"
---

[![Data Manipulation with R](https://d.gr-assets.com/books/1348665355m/3039427.jpg)](https://www.goodreads.com/book/show/3039427-data-manipulation-with-r)[Data Manipulation with R](https://www.goodreads.com/book/show/3039427-data-manipulation-with-r) by [Phil Spector](https://www.goodreads.com/author/show/625001.Phil_Spector)  
My rating: [4 of 5 stars](https://www.goodreads.com/review/show/1146896822)  
  
The quality that programming language based data analysis environments have that menu driven or batch environments do not is the ability to manipulate data. That means transforming data into usable forms, but it also means cleaning data, manipulating text, transforming data formats, and extracting data from free text. While R falls into this category of data analysis environment, almost all of the available material focuses on the application of statistical methods in R. This fills a much needed niche in how to process data. I still do not regard R as my goto tool for data manipulation, but this book means I am more likely to stay in R than otherwise. I used this as a textbook in a lower division data analysis course and the class went from a group that only half remembers Matlab to being able to process and analyze fairly large datasets. A comment I received was "I looked back on the work done in this project and I cannot believe I actually did that!"  
  
The first part of the book is reading in data and writing out results. It discusses both text (csv, delimited, fixed) and working with relational database. One note is that the database they use is MySQL. This was easily convertible to SQLite, which is what I used in my class because my students are not IT savvy. I also used supplementary material for SQL (which is readily available) Then putting things together into data frames.  
  
Next are a series of data types: datetimes, factors, numbers. For people who have only worked in Excel, these are deal breakers. Even using Excel, these are areas that often go unnoticed by students and lead to problems.  
  
Character manipulation is about working with strings and a gentle introduction to regular expressions. For many of my students, they have never manipulated text programmaticly before, so this chapter was quite successful. For Regular expressions, well it provided a taste of it, enough to solve the lab assignment. I supplemented it with other material, but noone was going to learn regular expressions in 5 pages.  
  
The best part of the book was the sections on aggregating and reshaping data. This is what made what my students were doing with R start to look like magic. Aggregations using the apply family of functions, reshape to convert data into long or wide formats, combining data frames, and an introduction to vectorization. This is not going to make anyone a functional programmer, but these are key idioms and Spector spent a lot of time here.  
  
I am not going to prefer R over Python for working with text and manipulating data, but Data Manipulation with R shows how to do some non-obvious things. The examples are all interesting enough to be useful, and they all work as is. And this goes deep enough into some pretty powerful capabilities that expanded my students understanding of what is possible. While it is becoming dated (an update would have to include dplyr), the approaches it provides put the reader well on their way to being an accomplished R programmer, not just someone who feeds data into functions.
  
  
[View all my reviews](https://www.goodreads.com/review/list/266417-louis)
