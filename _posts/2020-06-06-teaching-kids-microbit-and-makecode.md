---
title: "Teaching kids micro:bit and makecode during COVID-19 quarantine"
date: 2020-06-06
permalink: /posts/2020/06/teaching-kids-microbit-and-makecode/
tags:
  - "microbit"
  - "programming"
  - "teaching"
---

A couple of weeks into social distancing, as the kids various activities had shut down with no plan on how to open, we were faced with the question of how to keep our kids occupied. We have generally followed the principle of having one artistic, one physical, and one STEM activity ongoing per child (plus chinese), and for the older one we were trying to fill in the space opened as his robotics (First LEGO League) activity had closed down. And we wanted to have it be somewhat social, as we also wanted him to maintain his connections, as well as make sure there was a community of friends and relationships that may endure.  
  
For classmates, our first community that we reached out to were the other kids from his LEGO robotics group. I already had a number of email addresses from organizing an outing, and these were all kids who knew blockly style programming (or Scratch like) and programming in the physical world. The next source was a local chinese parent WeChat group. And we were looking for kids roughly the same age as DS9. And we found one more from a camp that DS9 was in last year.  
  
The goal was teaching programming, and for this, I choose block style programming, specifically on the BBC Micro:bit. The micro:bit was created for teaching introduction to computer science in Britain. They goal was a microprocessor that had on-board physical inputs and outputs, the ability to connect to other components, and could by taught by middle school teachers, who had a wide range of comfort level in teaching technology, and likely no comfort in teaching programming. Blockly style programming (using makecode) is particularly suited as it had enough range to allow the application of computer science basic concepts, but without issues such as syntax, which in normal text based programming often dominate an introductory computer science course. (in computer science, the concepts are the important part, syntax is merely the implementation. The focus in time and energy on syntax is considered a distraction)  
  
For materials, my mainstays of Adafruit and SparkFun were both unavailable. Adafruit was designated an essential business, but was focusing on medical suppliers. SparkFun was closed. So we had to source kits from Amazon.com, who was working from stock. The micro:bit itself was available, but kits tended to be from one of the multitude of unknown suppliers.  
  
For curriculum, I used the book micro:bit in Wonderland from Tech will save us. The target audience was people who could not program, and it was craft based, where the projects all had a programming component and a craft component (that interfaced with the micro:bit board through alligator clips and the touch pads. As an added bonus, there was a motivating reading, from Alice in Wonderland (which many people already owned, but was also free as it was in the public domain on Project Gutenberg.)

Some unit notes:

* Impacts of shutdown. The micro:bit was generally available on Amazon.com, but the kits of basic supplies were not. There were two sources that were left, the <https://www.techwillsaveus.com/>site and various no-name kits on Amazon.com The no-name kits tended to be breadboard based kits as opposed to alligator clip based kits. For elementary and middle school classes, the alligator based kits would have been much better
* Block coding on micro:bit was something the kids took to easily. Even the one who had no programming experience (meaning not even having background in Scratch). Using makecode was easy. By the second week everyone had a microbit (not necessarily a kit) and getting working makecode onto the micro:bit was not hard.
* First hard lesson was the control of the LED light, which was the first lesson that got off the micro:bit board. As this was really the first experience in physical computing, I believe that this is also considered a first milestone in electrical engineering. It took a lot of one-on-one attention to get everyone through this. But all of the other physical computing lessons (touch pads, connecting to sound speaker, other LED light projects) went much easier.
* If-else was not a problem
* Kids enjoyed the sound projects. Both the buzzer, then the music box.
* They also had no problem working through complicated if-else trees
* The big assignment here was to use the microbit as a musical instrument, which meant making lots of sounds (kids like noise)

Really, the only difficult week was the first experience with lighting a light bulb. While many students had experience with LEGO robotics and things like SPHERO, those kits deliberately hide the difficulties in connecting a controller to something off the controller. So after that, it becomes easier.

One thing I would do differently if I had to do this again, I would use the Sparkfun gator:circuit kit. It breaks out many comment electrical components and packages them along with resistors (needed to make sure that low resistance components like LED lights do not get burnt out) to make a alligator clip friendly board, which is much easier than trying to connect components on a bread board (I think Adafruit has components that do this to, but not packaged in a named kit). Leave the breadboard work for high school or later.

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg2rXEpBqT26S-pvwT-uWELmQ16-pfkh7ywP677Ps9L5LfKrGfidX_WsPVuL-9B8jSfWaDsIvudtVi1yP72WAF8uJa9w1830Ajb22MVa_GblPjJvdRHwKHpFlYh8z-5HiiI80pR/s320/zoomclasspicture20200531.png)

As this whole teaching kids programming experience was not nearly as traumatic as I thought it could be :-) there is going to be a follow-on. But instead of having the focus be technology and computing, the goal will be to actually use these skills to do something, so we are going to take the Sparkfun gator:science kit, which has electronic sensors that can be used with the microbit to create data collection lab instruments, as the basis for an investigative science course. And in true co-op style, there will be a team of parents who will be trying to teach the kids science. :-)

![](https://blogger.googleusercontent.com/img/proxy/AVvXsEh86QSBdeoW2PRLye5VFPX_YmIa_3XnjCMJwh2zM5fvmWLEqmx9nLeULfK-vNJgqXkpRDZ9FhAwqqZpfMzj7VBbBTmkh__mwIAs3fz1r0DJJplfa_7vFexQKtpAVTt5LTRJT9_zI0JsjEu1Hrplb8JURqe0uErHiQhZq8aUJ8oi83MRUADtAWT0Vfunmwv1HfF6-EbdTNCijJOS8_o1pWA9Tg=s320)
