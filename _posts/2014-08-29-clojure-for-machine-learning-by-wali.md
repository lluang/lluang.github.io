---
title: "Clojure for Machine Learning by Wali:  Book review"
date: 2014-08-29
permalink: /posts/2014/08/clojure-for-machine-learning-by-wali/
tags:
  - "data science"
  - "programming"
---

[![Clojure for Machine Learning](https://d.gr-assets.com/books/1399714777m/22062479.jpg)](https://www.goodreads.com/book/show/22062479-clojure-for-machine-learning)[Clojure for Machine Learning](https://www.goodreads.com/book/show/22062479-clojure-for-machine-learning) by [Akhil Wali](https://www.goodreads.com/author/show/8194937.Akhil_Wali)  
My rating: [3 of 5 stars](https://www.goodreads.com/review/show/1040187704)  
  
For a book that is about [programming language] for [computational task], there are two approaches. One is to assume basic competence in the language and teach the task, the other is to assume that the reader has basic competence in the task and teach how to do it in a language. This book assumes knowledge of Clojure and tries to teach machine learning. But I find that it does just enough to be dangerous. It has a series of methods but does not provide discussion on why you would choose once class of method over another, and it completely skips model evaluation. What this creates is someone who has a good idea of the mathematics and implementation of methods, but not when to use it or if it actually did what was intended.  
  
This makes me slightly different than the ideal audience of this book. I am learning Clojure and have only started using it for data analysis in real life. However, I have used Python and R for data analysis for several years now, and I have use both of them (and trained students to help me using both) for different machine learning projects (and I use R for teaching a course in data science).  
  
Each chapter in Clojure for Machine Learning takes a look of a class of machine learning algorithms and takes several looks at it. Generally, Wali looks at the mathematics and theory of the algorithm, then a simple implementation in Clojure, then some examples of using existing library implementations on a problem. The mathematical treatment seems nice, but it would not compare to an actual text on machine learning/data mining. And while seeing an implementation in Clojure has some value, I would have liked to have seen more humility in doing so (i.e. some recognition that there are limitations of an implementation that can actually fit into a book of this size with everything else that needs to be done).  
  
Two things that bother me about this after I finished was realizing that for each class of algorithms, the book only covers one or two methods. Which is fine, but it does not even acknowledge that there is a greater world. And as there is no discussion on how to perform model evaluation, an enthusiastic reader may reach the conclusion that they know what they are doing when implementing them against a data set and problem. Essentially, the enthusiastic reader knows enough to be dangerous and does not know what he does not know. If I were to suggest this book to someone, it would have to go with a severe caveat that what you know after this is how to set up a machine learning problem. More research has to be done to determine what actually needs to be done (the libraries used are much broader than what is covered) and then, learn from somewhere else how to evaluate or tune the methods used.  
  
In the end, I would treat this as a book of examples or cases of Clojure being used in machine learning. There is room in the world for a book on Clojure for machine learning, but this is not it.  
  
  
[View all my reviews](https://www.goodreads.com/review/list/266417-louis)
