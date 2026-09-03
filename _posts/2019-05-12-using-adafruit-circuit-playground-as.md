---
title: "Using an Adafruit Circuit Playground as a Makey Makey fruit piano"
date: 2019-05-12
permalink: /posts/2019/05/using-adafruit-circuit-playground-as/
---

One of the inspirations for the Adafruit Circuit Playground (CP) was the Makey Makey (http://www.makeymakey.com/), which provided a way to use touching conductive objects as input to a computer. Because of this, Makey Makey is commonly found in schools and maker faires as a means of connecting the world to electronics.  
  
Because the CP has 8 capacitive pads, it should be possible to do something similar with the CP. Using the serial monitor output, we can see what the CP registers through each pad, and set thresholds for an action, for example, lighting up an LED or playing a tone.  
  
The first version of the Makey\_cp used the Capacative touch pads directly to drive the LED and the speaker. By observing the capicative touch pads on the serial monitor we can see that the steady state value of the pads was between 1 and 10. Touching the pad increased the value to around 30, but often an adjacent pad would also increase in value as a finger affects the electric field around the adjacent pad. So we set a threshold on the CP capacitive to 20 for use as a finger piano. In addition, we use the switch to turn on and off the sound.  
  
The sound is tuned using the pitches.h definition file, which has the tones for each potential note. As the CP has 8 touch pads, this is enough for a full octave of a major or minor scale.  
  
To serve as a Makey Makey, the pads need to be connected via alligator clips to something that can conduct electricity, such as fruit or a metal conductor. Because such objects have capacitance, the noise level on the CP touch pads increases. In order to increase the signal from touching the pads, the person touching the pads should be connected to a power source, in this case we use alligator clips to the 3.3V out pad of the CP. This leads to the CP to detect a value of approximately 150.  
  
Next, we attach alligator clips to the eight capacitive pads and to fruit. This creates a fluctuating reading around 20. We find through the serial monitor that touching the fruit while connected to the 3.3V out leads to a capacitance reading of around 225. The threshold is then
