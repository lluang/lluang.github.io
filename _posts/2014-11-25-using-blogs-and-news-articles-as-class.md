---
title: "Using blogs and news articles as class mini-cases - How discrete-event simulation can help project prison populations"
date: 2014-11-25
permalink: /posts/2014/11/using-blogs-and-news-articles-as-class/
tags:
  - "operations research"
  - "teaching"
---

[How discrete-event simulation can help project prison populations](http://blogs.sas.com/content/subconsciousmusings/2014/10/16/how-discrete-event-simulation-can-help-project-prison-populations/) (SAS Subconscious Musings)
  

My experiment this semester is more intensive use of news articles as subjects for in-class discussion of examples of applications of what we are learning. While I have done this in the past, this semester I made it a deliberate plan to discuss one article a week in each class. So far this semester in my simulation and decision models classes, I have covered reactions to the W. Africa Ebola outbreak, Game 7 of the 2014 World Series, Gamergate, flu vaccinations, commercial manned space transport, pulling a goalie in hockey, cargo shipping, business expansion, business divestiture, automation of manufacturing, health care system operations, among other things.

I identify articles through the use of RSS feed aggregators. My news feed includes a number of feeds from a range of business school professors focusing on supply chain and operations management issues. I follow the CDC MMWR as well as the journal Health Affairs to get health care related articles. And the New York Times front page and Google News are good for a lot of different stories. The key is finding an article where the reporter was good enough to discuss the various options that were available and enough details that you can figure out the values of various actors involved.

The key a good class case article is that there are potentially reasonable alternatives to discuss. In the decision models course, the discussion revolves around identifying the courses of action available, the sequence in which decisions need to be made and information becomes available, assessing the attributes (values) of the people involved, then assessing how they may assess probabilities of various events.

For the simulation course, the focus on case discussions is on understanding how a decision maker in the article may use the simulation, then we do a whiteboard exercise where we draw out an event graph diagram to model that system, focusing on what needs to be included (states, events) based on the decision maker needs. The goal is to discuss modeling in a specific context, so we can talk about what needs to be included, and what does NOT need to be included in the model to fit the particular purpose. The contrast is to the textbook homework problems, which generally provide a very specific context and set of details which have be included in the model to answer the homework problems. Textbook problems generally do not include thinking about modeling in such a way to determine what is the right question and how to simplify the model to address the question.

Last week we looked at the decisions made by the North Carolina Sentencing commission. Unlike most cases, in this case we happen to know for a fact that a simulation was used in the decision making process.  
  
Our discussion began with purpose: why would the North Carolina Sentencing Commission be interested in a simulation of prison population. We came up with the need to plan prison space, make arrangements with neighboring states to house NC prisoners, and to allocate resources to monitor parolees.  
  
Next, a discussion of what would the simulation need to track to fulfill the purpose of the NCSC. This would include the number of prisoners and the number of parolees. And the time remaining for each prisoners sentences. Then, we have the state of the system being the prisoners and parolees, and the terms of sentencing. (we decided not to discuss the size of the prison, since that is something that was being determined).  
  
The last part of the discussion was where the typical homework or exam problem started, diagramming the events tracked by the system, how each events changes the system state, and then how to generate delays in the simulation.  
  
The purpose of the exercise was to discuss modeling. Not in terms of how you build a model from a system description, but to think through how to model and make modeling trade-offs given the decision that needs to be made about a specific system. The cost of this discussion is time, doing this results in us not completing a semester syllabus of a class that is quite analytical. But, as textbooks usually begin modeling examples with a system description and a purpose, I think it adds to the course and I think the compromise is worth it.  
  
Thanks to Natalia, Jeff, and Leo from SAS for our conversations about this particular SAS case at the INFORMS conference. It enriched the class discussion to know what was happening behind the scenes of the Subconscious musings blog article.
