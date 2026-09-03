---
title: "Lessons in teaching: teaching exploratory data analysis with R"
date: 2015-07-28
permalink: /posts/2015/07/lessons-in-teaching-teaching/
tags:
  - "data science"
  - "database"
  - "teaching"
---

Last spring, I took over a course labeled as information systems engineering. This is aimed at sophomores in engineering. Historically, this course focused on using the MS Access database. I was asked by the department to take this over after several years of commenting that our engineering seniors have inadequate computer programming skills, as evidenced by the amount of effort they spend on their senior projects doing tasks that would have been much simpler if they tried programming. Last year some of the faculty tried experiments in their classes where they had students code in an assignment (generally they asked for C). In every case this went very badly. So they asked me to take this course and change it so that it covered programming and specifically to use R. (I am effectively the primary data analysis faculty here). In keeping with the course title, I chose to focus the course on data analysis, with one month focusing on databases and how to think about data problems (and giving them time to gradually learn R), the rest on exploratory data analysis. I used as the primary text Data Manipulation with R by Phil Spector, and as supplements GGplot2 by Hadley Whickam and An Introduction to Data Cleaning by Edwin de Jonge and Mark Van Der Roo. I presented the CONVO framework for thinking about data problems based on Thinking about Data by Max Shrum.  
  
As freshmen, they would have has CS0 (the Association for Computing Machinery designation of introduction to computer science for non-computer science/electrical engineering majors) material covered over a two course sequence that also covers mathematics for engineering (primarily linear algebra). The language of instruction is primarily Matlab, but they also cover C and, depending on instructor, Python (there is one module that is sometimes covered by Physics faculty, and they like to use Python). For databases, there is another course on databases taught by an adjunct faculty who used to teach databases for information systems.  
  
For tools I used SQLite (more on why this and not MS Access later), SQLite Manager, R, and R Studio. Prior to the end of the previous semester I sent everyone an email with links to videos introducing them to R and R Studio and encouraged them to introduce them to R through typing out a tutorial (I explained that they would actually learn R over the semester, the typing exercise was to ensure they had seen everything once before we actually needed it in class.).  
  
For assessments, there were weekly labs for computer knowledge, exams mostly covered how to think through data problems. A semester project with two milestones (plus completed project) was the main way to assess how well they developed computer programming competency. Each week, we covered one  
  
We had three datasets that I used as teaching and lab examples throughout the course.  
  

1. Titanic survivors
2. National Survey of Family Growth
3. American Community Survey (U.S. Census, Pittsburgh North PUMA)

  
  
Some observations and notes  
  
1. SQLite vs MS Access. I was surprised to find out that MS Access has a relatively low size limit on databases. It was not able to handle either the National Survey of Family Growth (expected) nor could it handle a single PUMA for the American Community Survey (this was a surprise). That meant we had to use SQLite for the entire course. (my Mac students were happy since this put them on equal footing with the PC students). Next time I will just use SQLite. (and use MS Access only to explain why we are not using MS Access)  
  
2. Learning R. In a pre-class survey, the entire class indicated complete lack of confidence in programming to fulfil a task (expected). I think that the standard programming language belief that it is always easier to learn a second programming language failed in this case, because I did not realize just how bad their first experience was. While the first month was very intentionally a confidence building exercise, I think that for a portion of the class, they really needed to start from scratch. Next time around, I will spend an entire period doing nothing but walking the class through R.  
  
3. Data manipulation. This included covering data structures (text, dates, dataframes), regular expressions, plyr, reshape, and missing values imputation. Essentially the Hadleyverse v. 1. One issue here was the wide variety of potential topics. While I think every topic got used by someone in their semester project, some of the student evaluations complained about my teaching topics that were not on the exam. Essentially, for people who are only used to computing on numbers, the entire topic of data manipulation seems to be a heavy cognitive load.  
  
4. Visualization. I taught qplot, but I think that I should have gone straight to ggplot. I think that either I go the traditional route and build every type of plot as an individual entity, or I present the grammar of graphics approach and build plots. Either way, now that I've taught it, I don't think qplot helps in either, and it is a lot less capable. (every groups final project pretty much had to transition to ggplot)  
  
5. Projects. I let the students find their own datasets and questions, subject to the fact that they had to write the project purpose using the guidelines we covered in thinking about data. The big division in quality of the projects was the richness of the dataset. Next time, I will be a lot more strict on the dataset, in particular, I had a subjective guideline that they should not consider it practical to look at the whole dataset. In some cases, this still was a very small volume, and it made for a trivial and uninteresting report.  
  
6. Thinking about data. I used Max Strum Thinking about data framework where for a data project, one should identify the COntext, Need, Vision, Outcome. Every week we read a contemporary news article that included a data component (mostly from the fivethirtyeight.com website) Each discussion opened up with class discussion to summarize the article into this CONVO framework, then a discussion of the analysis in the article itself. This actually worked out pretty well. Each exam had at least one CONVO focused question, and generally they did well (and of the people who did not, there were no surprises based on class participation)  
  
7. News articles. I had a wide range of news articles that we covered in a weekly discussion, drawn mostly from fivethirtyeight.com, the Upshot column from the New York Times, and the data series from the Washington Post. Each article was assigned at the end of the week, for discussion in the Tuesday morning lecture. Discussion opened up with a summary based on the CONVO framework, then we evaluated the data analysis presented in the article, followed by how we could change it to make it better or to answer a different question. These class periods were fun. My goal was to take 15 minutes for each article, in a few cases we were on a roll so we let it go to 30 minutes. I had good participation. And it showed in the CONVO question on exams, and generally people did well when I asked them to imagine a data analysis based on data presented on a test (this was the last part of a multi part question, where the other parts were about the data presented). One disappointing thing was that when it came time for course evaluations, I was rated poorly with how the class material relates to the everyday world (like all engineering courses do). So I have to figure this one out.  
  
8. Course evaluations. When course evaluations came in, they were roughly a uniform distribution, which makes them very hard to interpret. In addition, comments that expressed weaknesses were mirrored in the comments that expressed strengths. So that meant that I had terrible averages and a chat with my department chair. Fortunately for me, the generally accepted belief is that the broad diversity in the teaching evaluation is due to pushing the students harder (i.e. making them do programming again) and that this is part of improving the department as a whole. Hopefully when he meets the dean to review the faculty the dean agrees with this assessment as well.  
  
9. Class projects. About a quarter of the projects (teams of1, 2, or 3) were genuinely impressive. Many projects with 100,000s of records, a few with millions of records, several dimensions, and data analysis that used layered visualizations to explore. Most projects were a little more modest, thousands of data points and reasonable visualizations. Some projects were personal in nature (looking at issues in their home towns), others were fun (several projects revolved around music or sports) A number showed evidence of lack of confidence, shown in very unambitious data sets. The issue with this group is how hard to push. One of the known problems with CS0 or CS1 is that they complete destroy people's confidence in programming, and a substantial portion of those who take one of their courses completely leave the field, or in the case of engineers, avoid programming at all costs in the future.  
  
Next time around:  
  
1. Using a framework like CONVO (Max Strum) works. I am pretty sure everyone at least learned how to think about problems and settings.  
2. Skip MS Access. I think I probably spent too much time on databases and working with the MS Access interface. Next time, going straight to SQL is probably enough, given that the limits on MS Access means that we cannot do interesting datasets.  
3. I liked using three datasets the entire course. Actually, some of them used the American Community Survey for their semester projects (after reading in multiple PUMA, e.g. an entire metropolitan area instead of only one PUMA).  
4. One question that I will have to think about is how much of a do-over of CS0 this course will be. Clearly, as it is most of the class seems to get it the second time around and a good portion are pretty impressive. But there is a pretty large fraction that finished CS0 absolutely convinced that programming is forever beyond them.
