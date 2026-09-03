---
title: "Reflections on the Advent of OR: Using Generative AI in Analytics and Agile Operations Research"
date: 2025-12-29
permalink: /posts/2025/12/reflections-on-advent-of-or-using/
tags:
  - "agile methodology"
  - "generative AI"
  - "operations research"
---

In December 2025 I participated in the Advent of OR (https://adventofor.com) which was a 24 day exercise that guided participants through an optimization project. And instead of just solving problems and creating models, the Advent of OR walked through an entire project life cycle, using the INFORMS Analytics Framework.

  

While I am not a student or early career who was the target audience, I took part, and I had three goals.

  

1. Use a new programming toolkit. I used VS Code with R and Quarto. I usually use R Studio and I wanted to try R on VS Code. And I think Quarto is the future replacing Jupyter Notebooks for Python and a natural evolution from R Markdown.

2. Practice in optimization. In the Operations Research world, I am NOT an optimization person. My thesis was applied probability (queuing) and my methods research has been in simulation (one stream in ranking & selection and another stream in Bayesian methods for input modeling)

3. Using Generative AI. I wanted to see how generative AI does in an operations research project. And I wanted to do it right in a setting where I can give it references to guide it. Note: I have found that Generative AI favors descriptive statistics, machine learning, and hypothesis based statistics over other forms of analytics, so it needs some guidance.

  

### Toolkit

  

I had to set up VS Code with the R extensions, Quarto (and extension), ompr and the glpk with associated R ROI packages, and to make sure everything worked, I download the repository for OR\_using\_R by Tim Anderson. Then to render the book (meaning I made sure all the code ran) I had to install texlive with xetex and extra fonts. Generative AI (I had Gemini CLI installed) was very helpful in all of the system administration tasks since it could figure out what was needed every time there was an error message.

  

### Data analysis and Optimization

  

Working with the data sets, it read in the data, (I had to give it some corrections along the way to help it recognize the data types. When the data files were read in, it recognized that the data sets did not correspond in granularity. In the R markdown file it created, in addition to generating the code that read in the data and created summaries, it also identified a number of questions and concerns about the data and created questions for the stakeholder. This was a good set of questions that corresponded to what others put forward.

  

It also did well with the optimization. Given an optimization textbook, I first asked the generative AI for a mathematical formulation based on the project description. Similarly, it created a process for determining what kind of problem this was and worked through that process to determine that this was a linear programming optimization problem.

  

Next was a LP formulation using OMPR. The first formulation was straight forward. I went and had the GenAI break out the formulation into its own R script to enforce a separation of concerns between the data handling, optimization model, and output processing.

  

I generally also ask for docstrings as I go, and the Gen AI did this for both the model as well as various handling functions. I generally read the docstrings to ensure they say what I expected them to say. When it did not, since the docstrings were written based on the code, I took it to mean that the code was not right (this exposed a mistake in the initial formulation of the LP in OMPR). Similarly, I had the Gen AI write unit tests for the constraints and a mock problem to test the optimization.

  

### Agile Operations Research

  

One of the aspects of having the Advent of OR over 24 days is that it rotates topics between the art of modeling, implementing and managing models, and interactions with stakeholders. There are a couple of very important points. First is that interacting with stakeholders is not something that is at the beginning and end of project and ignored in the middle. There needs to be stakeholder engagement throughout the modeling process. A second point that has come out in the conversations on LinkedIn is that the most common cause of project failure across data analytics are communication failures, in particular between the analyst and the end customer. While this can have many causes (including management inserting themselves in between the analyst and end customer), as analysts we must have that direct interaction from the beginning of the project (business problem formulation in the INFORMS Analytics Framework)

  

In the early stages of the project, one factor we need to face is failure of imagination. The first level for analytics is that our stakeholders often do not know what is possible across the full range of analytics. Often a problem is presented as a request for a tool, but for the results of the project to have any value, it has to address the end problem, so business problem formulation has to start with the end problem, determine what kind of information from data can help the decision makers address the problem, and then we can start discussing what methods can provide results in the form that will be useful. Currently, because of media hype, the initial request can be for a dashboard, or a predictive model, or a generative AI tool. As operations research analysts we can also bring to bear statistics, forecasting, optimization, simulation, and queueing; and different ways of applying those methods to give different kinds of results that can be delivered to decision makers to make better decisions.

  

After the business problem formulation, the next big change in the project will occur when presenting the first minimum viable model to the end user. This is the first model that uses a minimum acceptable subset of the data and model that covers the most essential aspects of the smallest version of the problem. The reason this is important is before this, all conversations are abstract and theoretical. The first time a model with outputs is presented to an end user, the end user will start to imagine how they would use these results in real situations that have happened in the past. And they will start telling about all of the considerations they account for, the information they need to gather to make decisions, and who they need to consult and coordinate with. And this can change the entire project. And from experience, I do not think it matters how much work is done at higher levels to define the project, the first time a model is presented to an end user the project will change so that the outcomes can be usable to the business. So it is best to make that happen as early as possible so that change causes the least disruption to the work in progress.

  

The idea of rapid cycles of iteration and feedback from the customer, and the willingness to accept changes to the project due to that interaction are the hallmarks of agile development methodologies in the software development world. Having regular rounds of model iteration where additional elements are added to the model, and getting feedback from stakeholders to confirm that the project is on the right track to produce something useful. And just like the software development world has experienced, this is more likely to lead to useful product, and actually faster than attempting to follow a rigid path that leads to something irrelevant.

### Conclusion

  

The Advent of OR proved to be a valuable exercise, offering a full-cycle project experience that highlighted two critical modern aspects of Operations Research: the integration of Generative AI and the necessity of an Agile approach. Generative AI demonstrated significant utility in accelerating system setup and basic modeling tasks, freeing up the analyst for higher-level problem-solving. More importantly, the experience reinforced that project success hinges on continuous, direct stakeholder engagement, mirroring the principles of Agile development. By prioritizing early delivery of a Minimum Viable Model, analysts can gain crucial feedback that aligns the project with real business needs, ultimately reducing the risk of communication-based failure and ensuring the final product is relevant and utilized.
