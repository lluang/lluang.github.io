---
title: "Testing in pairs: The Global Day of Coderetreat"
date: 2014-11-16
permalink: /posts/2014/11/testing-in-pairs-global-day-of/
tags:
  - "programming"
---

**[Global day of Coderetreat](http://gdcr.coderetreat.org/): a day to celebrate passion and software craftsmanship**  
  
A [Coderetreat](http://coderetreat.org/) is like a master class for computer programmers. It is a chance to view programming as a craft that can be practiced and honed. And like other crafts, the way you develop skill and creativity is to create limits, then use your creativity to accomplish the goal while working around the limits.  
  
As an engineer, I am not primarily a programmer, although I have some level of skill, so this is not the typical view of programming, which is viewed more as a tool and a necessary evil. The effect is that improved competency is not valued, which leads to inability to deal with dirty data, models that cannot be implemented, and results that cannot be reproduced.  
  
Code retreat is build around the four principles of simple design, due to [Kent Beck](https://twitter.com/#!/kentbeck):   
  
  
  

1. Runs all the tests
2. Expresses every idea that we need to express
3. Says everything once and only once
4. Has no superfluous parts

The structure of the Coderetreat is six sessions where we work with Conway's Game of Life. For each session, we pair with a different partner. In addition, in each session we are to begin from scratch, and there is a twist to the rules. The goal was never to actually implement the Game of Life (although in two cases we actually had all of the parts working and tested), but to spend time working with someone else on code.

**Observations**

1. Pair programming. This was my favorite aspect of the Coderetreat, pairing with six different people. I figure there were two where I was generally more skilled, two where I was generally less skilled, and two where we were pretty much even. In every case our end solutions had very different designs as it was a combination of our different ways of looking at things and our experiences of having tried different designs in previous sessions, and the skill levels of the people involved. When I worked with students, we would occasionally have a session where we worked together to solve a problem, and some of my students have commented that they found those sessions to be invaluable because they had a chance to watch how I worked and saw how I dealt with different types of problems. But this time I did pair programming on people on a much more even footing and I get to experience it as well. It showed in how we used different tools (although I was experimenting with a new IDE), how we solved problems in code and how we solved logic problems.

2. Test driven development (TDD). I've heard of the concept before, and I have even contributed to a unit test framework, but I've never really done it. What TDD did was to encourage more modular code. It also forced us to put more thought into our design, as we had to consider what information was required an in what format to do what we needed. In one session, one member of the pair would write tests and the other would write the code, and the two were not allowed to communicate. As the one writing the tests, since we could not otherwise communicate, I realized that in writing the tests I was forcing a set of data structures and a design in my tests.

3. Throwing away dsigns. We started each session with a clean code base. What it meant was that we did each session using the lessons from what went before. The first two sessions we did not get much progress, but the third was the one where we made the most progress, as we basically learned from the combined mistakes made over the first two sessions and designed the tests with the past problems faced in mind, and the solution was fairly easy after that. That was good because the next three sessions were the ones with the wierder twists.

4. New languages. Python is by far my strongest language, but I did one session in Clojure and one session with Java. In both cases I learned a lot about how people set up their tools and the idioms they used, which were different than what you see in standard texts.

5. Dealing with constraints. There were three weird twists. One was mute pairs, one was limitations on the size of methods, one was no use of conditional statements. Mute pairs forced the design to be simple and clear (especially difficult because we did it in Clojure, which I barely can say I know without the aid of a book in front of me), the size of methods led us to generate very ugly method/class hierarchy to deal with the extreme restrictions, no conditionals lead to a range of creative hacks. This has an effect similar to a lot of exercises done in the creative arts, adding constraints is one way of encouraging more creativity.

This was a valuable experience. Most of the people there had computer science backgrounds, and pairing with them taught me a lot. And I was somewhat glad to know I could add to people's knowledge base as well.

Thanks to Code &amp; Supply (@codeandsupply) and Think Through Math (@ThinkThroughMath) for making this event possible and for helping to keep it free, and to IBM for hosting.

[![Pittsburgh Code & Supply Logo](https://cdn.evbuc.com/eventlogos/21329480/logoextrasmall.png "Pittsburgh Code & Supply")](http://www.codeandsupply.co/)
  

[![Think Through Math logo](https://cdn.evbuc.com/eventlogos/21329480/imglogottm.jpg "Think Through Math")](http://www.thinkthroughmath.com/)
