---
title: "ESP8266 Thing board based environmental monitor"
date: 2016-10-28
permalink: /posts/2016/10/esp8266-thing-board-based-environmental/
tags:
  - "arduino"
  - "making"
---

The goal of this project was to create an automatic temperature and light level monitor for a bioshelter (greenhouse +) run by The Bible Center Oasis Project (Pittsburgh, PA). Because it would be used to grow flora and fauna, it needed ongoing monitoring of temperature and light levels to confirm that it would support the growth of food, and to monitor the effectiveness of measures being explored to control environmental conditions.  
  
  

|  |
| --- |
| [Homewood, Pittsburgh , PA](https://www.flickr.com/photos/lugerla/28207669745/in/album-72157674294396515/ "Homewood, Pittsburgh , PA") |
| Bible Center Oasis Project bioshelter in Homewood (Pittsburgh), PA |

  

As an off-grid, solar powered greenhouse, the bioshelter is not connected to any utilities. So any environmental monitoring solution needed to be low powered and use wi-fi for communication (i.e. no phone line). We also preferred solutions that did not force a subscription to a specific data logging service.

|  |
| --- |
| [Temperature, humidity and light monitor](https://www.flickr.com/photos/lugerla/29770814972/in/album-72157674294396515/ "Temperature, humidity and light monitor") |
| Sparkfun ESP8266 Thing Dev board based monitor |

  
I developed a solution based on the [Sparkfun ESP8266 Thing development board](https://www.sparkfun.com/products/13711). This board provided the Arduino microcontroller to control the project and on-board wifi with antenna. The other major components of the board were:

* Sparkfun ESP8266 Thing Dev board
* [SparkFun Atmospheric Sensor Breakout - BME280](https://www.sparkfun.com/products/13676) for temperature, humidity, and barametric pressure sensors
* [SparkFun Luminosity Sensor Breakout - TSL2561](https://www.sparkfun.com/products/12055) for the luminosity sensor

I first soldered headers onto the ESP8266 Thing dev board and the BME280 and TSL2561 breakout boards. These allowed for use of two [mini-breadboards](https://www.sparkfun.com/products/12044) to develop the monitor, which also served as a base for the project when deployed.  
  
The Thing dev board and both breakout boards were set up with Inter-integrated Circuit (I2C), protocol, so both sensor boards were connected to the I2C inputs on the Thing dev board.  
  
The Thing dev board was then programmed to transmit the response to a [phant server](http://phant.io/). Specifically, the [data.sparkfun.com](http://data.sparkfun.com/) server that is made freely available by Sparkfun. In addition to being a data display, the phant server allows for accessing the data as csv or json files for further analysis, or using [analog.io](http://analog.io/s8XH) (link opens up the live graph of data. analog.io an IoT platform made available by Luke Beno). Because phant also exposes the data in JSON format, my usual way of working with the data is to use the jsonlite package within R.  
  

|  |
| --- |
|  |
| Breadboard diagram of ESP8266 with BME280 and TSL2561 |

  
  
Arduino \*.ino code

```python
1:  // Include the ESP8266 WiFi library. (Works a lot like the  
2:  // Arduino WiFi library.)  
3:  // Uses BME280 and TSL2561 to record temperature, pressure, humidity, and lux data to phant  
4:  // Code  
5:  //   
6:  #include ;  
7:  #include ;  
8:  #include ;  
9:  #include "Wire.h"  
10:  #include "SPI.h"  
11:  // Include the SparkFun Phant library.  
12:  #include ;  
13:  // Include SparkFun BME280 library  
14:  #include "SparkFunBME280.h"  
15:  //Global sensor object  
16:  BME280 mySensor;  
17:  // SFE_TSL2561 object  
18:  SFE_TSL2561 light;  
19:  //////////////////////  
20:  // WiFi Definitions //  
21:  //////////////////////  
22:  const char WiFiSSID[] = "ssid";  
23:  const char WiFiPSK[] = "psk";  
24:  /////////////////////  
25:  // Pin Definitions //  
26:  /////////////////////  
27:  const int LED_PIN = 5; // Thing's onboard, green LED  
28:  const int ANALOG_PIN = A0; // The only analog pin on the Thing  
29:  const int DIGITAL_PIN = 12; // Digital pin to be read  
30:  ////////////////  
31:  // Phant Keys //  
32:  ////////////////  
33:  const char PhantHost[] = "data.sparkfun.com";  
34:  const char PublicKey[] = "publickey";  
35:  const char PrivateKey[] = "privatekey";  
36:  /////////////////  
37:  // Post Timing //  
38:  /////////////////  
39:  const unsigned long postRate = 1000*60 * 30;  
40:  unsigned long lastPost = 0;  
41:  // Global variables for TSL2561:  
42:  boolean gain;   // Gain setting, 0 = X1, 1 = X16;  
43:  unsigned int ms; // Integration ("shutter") time in milliseconds  
44:  void setup()  
45:  {  
46:   // initHardware(); // Setup input/output I/O pins  
47:   connectWiFi(); // Connect to WiFi  
48:   digitalWrite(LED_PIN, LOW); // LED on to indicate connect success  
49:   //For I2C, enable the following and disable the SPI section  
50:   mySensor.settings.commInterface = I2C_MODE;  
51:   mySensor.settings.I2CAddress = 0x77;  
52:   //***Operation settings*****************************//  
53:   mySensor.settings.runMode = 3; // 3, Normal mode  
54:   mySensor.settings.tStandby = 0; // 0, 0.5ms  
55:   mySensor.settings.filter = 0; // 0, filter off  
56:   //tempOverSample can be:  
57:   // 0, skipped  
58:   // 1 through 5, oversampling *1, *2, *4, *8, *16 respectively  
59:   mySensor.settings.tempOverSample = 1;  
60:   //pressOverSample can be:  
61:   // 0, skipped  
62:   // 1 through 5, oversampling *1, *2, *4, *8, *16 respectively  
63:    mySensor.settings.pressOverSample = 1;  
64:   //humidOverSample can be:  
65:   // 0, skipped  
66:   // 1 through 5, oversampling *1, *2, *4, *8, *16 respectively  
67:   mySensor.settings.humidOverSample = 1;  
68:   // Initialize the SFE_TSL2561 library  
69:   // You can pass nothing to light.begin() for the default I2C address (0x39),  
70:   // or use one of the following presets if you have changed  
71:   // the ADDR jumper on the board:  
72:   // TSL2561_ADDR_0 address with '0' shorted on board (0x29)  
73:   // TSL2561_ADDR  default address (0x39)  
74:   // TSL2561_ADDR_1 address with '1' shorted on board (0x49)  
75:   // For more information see the hookup guide at: https://learn.sparkfun.com/tutorials/getting-started-with-the-tsl2561-luminosity-sensor  
76:   light.begin();  
77:   Serial.begin(57600);  
78:   Serial.print("Program Started\n");  
79:  // The light sensor has a default integration time of 402ms,  
80:   // and a default gain of low (1X).  
81:   // If you would like to change either of these, you can  
82:   // do so using the setTiming() command.  
83:   // If gain = false (0), device is set to low gain (1X)  
84:   // If gain = high (1), device is set to high gain (16X)  
85:   gain = 0;  
86:   // If time = 0, integration will be 13.7ms  
87:   // If time = 1, integration will be 101ms  
88:   // If time = 2, integration will be 402ms  
89:   // If time = 3, use manual start / stop to perform your own integration  
90:   // Use time = 1 so that the midday sun does not lead to an error  
91:   unsigned char time = 1;  
92:   // setTiming() will set the third parameter (ms) to the  
93:   // requested integration time in ms (this will be useful later):  
94:   Serial.println("Set timing for TSL2561...");  
95:   light.setTiming(gain,time,ms);  
96:   // To start taking measurements, power up the sensor:  
97:   Serial.println("Powerup light sensor...");  
98:   light.setPowerUp();  
99:   // The sensor will now gather light during the integration time.  
100:   // After the specified time, you can retrieve the result from the sensor.  
101:   // Once a measurement occurs, another integration period will start.  
102:   Serial.print("Starting BME280... result of .begin(): 0x");  
103:   delay(10); //Make sure sensor had enough time to turn on. BME280 requires 2ms to start up.  
104:   //Calling .begin() causes the settings to be loaded  
105:   Serial.println(mySensor.begin(), HEX);  
106:  }  
107:  void loop()  
108:  {  
109:   unsigned int delaytime;  
110:   Serial.println("Posting to Phant!");  
111:   if (postToPhant())  
112:   {  
113:    lastPost = millis();  
114:    Serial.println("Post Suceeded!");  
115:   }  
116:   else // If the Phant post failed  
117:   {  
118:    Serial.println("Post failed, will try again.");  
119:   }  
120:   delaytime = postRate;  
121:   delay(delaytime); // Short delay, then next post  
122:  }  
123:  void connectWiFi()  
124:  {  
125:   byte ledStatus = LOW;  
126:   Serial.println();  
127:   Serial.println("Connecting to: " + String(WiFiSSID));  
128:   // Set WiFi mode to station (as opposed to AP or AP_STA)  
129:   WiFi.mode(WIFI_STA);  
130:   // WiFI.begin([ssid], [passkey]) initiates a WiFI connection  
131:   // to the stated [ssid], using the [passkey] as a WPA, WPA2,  
132:   // or WEP passphrase.  
133:   WiFi.begin(WiFiSSID, WiFiPSK);  
134:   // Use the WiFi.status() function to check if the ESP8266  
135:   // is connected to a WiFi network.  
136:   while (WiFi.status() != WL_CONNECTED)  
137:   {  
138:    // Blink the LED  
139:    digitalWrite(LED_PIN, ledStatus); // Write LED high/low  
140:    ledStatus = (ledStatus == HIGH) ? LOW : HIGH;  
141:    // Delays allow the ESP8266 to perform critical tasks  
142:    // defined outside of the sketch. These tasks include  
143:    // setting up, and maintaining, a WiFi connection.  
144:    delay(100);  
145:    // Potentially infinite loops are generally dangerous.  
146:    // Add delays -- allowing the processor to perform other  
147:    // tasks -- wherever possible.  
148:   }  
149:   Serial.println("WiFi connected");  
150:   Serial.println("IP address: ");  
151:   Serial.println(WiFi.localIP());  
152:  }  
153:  void initHardware()  
154:  {  
155:   Serial.begin(57600);  
156:   pinMode(DIGITAL_PIN, INPUT_PULLUP); // Setup an input to read  
157:   pinMode(LED_PIN, OUTPUT); // Set LED as output  
158:   digitalWrite(LED_PIN, HIGH); // LED off  
159:   // Don't need to set ANALOG_PIN as input,  
160:   // that's all it can be.  
161:  }  
162:  int postToPhant()  
163:  {  
164:   // LED turns on when we enter, it'll go off when we  
165:   // successfully post.  
166:   digitalWrite(LED_PIN, LOW);  
167:  // Retrieve the data from the device:  
168:   unsigned int data0, data1;  
169:   double lux;  // Resulting lux value  
170:   boolean good; // True if neither sensor is saturated  
171:   if (light.getData(data0,data1))  
172:   {  
173:    // getData() returned true, communication was successful  
174:    Serial.print("data0: ");  
175:    Serial.print(data0);  
176:    Serial.print(" data1: ");  
177:    Serial.print(data1);  
178:    // To calculate lux, pass all your settings and readings  
179:    // to the getLux() function.  
180:    // The getLux() function will return 1 if the calculation  
181:    // was successful, or 0 if one or both of the sensors was  
182:    // saturated (too much light). If this happens, you can  
183:    // reduce the integration time and/or gain.  
184:    // Perform lux calculation:  
185:    good = light.getLux(gain,ms,data0,data1,lux);  
186:    // Print out the results:  
187:    Serial.print(" lux: ");  
188:    Serial.print(lux);  
189:    if (good) Serial.println(" (good)"); else Serial.println(" (BAD)");  
190:   }  
191:   else  
192:   {  
193:    // getData() returned false because of an I2C error, inform the user.  
194:    byte error = light.getError();  
195:    printError(error);  
196:   }  
197:   // Declare an object from the Phant library - phant  
198:   Phant phant(PhantHost, PublicKey, PrivateKey);  
199:   // Add the three field/value pairs defined by our stream:  
200:   phant.add("temp_f", mySensor.readTempF());  
201:   phant.add("humidity", mySensor.readFloatHumidity());  
202:   phant.add("pressure_kpa", mySensor.readFloatPressure()/1000);  
203:   phant.add("lux", lux);  
204:   // Now connect to data.sparkfun.com, and post our data:  
205:   WiFiClient client;  
206:   const int httpPort = 80;  
207:   if (!client.connect(PhantHost, httpPort))  
208:   {  
209:    // If we fail to connect, return 0.  
210:    return 0;  
211:   }  
212:   // If we successfully connected, print our Phant post:  
213:   client.print(phant.post());  
214:   // Read all the lines of the reply from server and print them to Serial  
215:   while(client.available()){  
216:    String line = client.readStringUntil('\r');  
217:    //Serial.print(line); // Trying to avoid using serial  
218:   }  
219:   //Print each row in the loop  
220:   //Start with temperature, as that data is needed for accurate compensation.  
221:   //Reading the temperature updates the compensators of the other functions  
222:   //in the background.  
223:   Serial.print(mySensor.readTempC(), 2);  
224:   Serial.print(",");  
225:   Serial.print(mySensor.readTempF(), 3);  
226:   Serial.print(",");  
227:   Serial.print(mySensor.readFloatPressure(), 0);  
228:   Serial.print(",");  
229:   Serial.print(mySensor.readFloatAltitudeMeters(), 3);  
230:   Serial.print(",");  
231:   Serial.print(mySensor.readFloatAltitudeFeet(), 3);  
232:   Serial.print(",");  
233:   Serial.print(mySensor.readFloatHumidity(), 0);  
234:   Serial.print(",");  
235:   Serial.print(lux);  
236:   Serial.println();  
237:   // Before we exit, turn the LED off.  
238:   digitalWrite(LED_PIN, HIGH);  
239:   return 1; // Return success  
240:  }  
241:  void printError(byte error)  
242:   // If there's an I2C error, this function will  
243:   // print out an explanation.  
244:  {  
245:   Serial.print("I2C error: ");  
246:   Serial.print(error,DEC);  
247:   Serial.print(", ");  
248:   switch(error)  
249:   {  
250:    case 0:  
251:     Serial.println("success");  
252:     break;  
253:    case 1:  
254:     Serial.println("data too long for transmit buffer");  
255:     break;  
256:    case 2:  
257:     Serial.println("received NACK on address (disconnected?)");  
258:     break;  
259:    case 3:  
260:     Serial.println("received NACK on data");  
261:     break;  
262:    case 4:  
263:     Serial.println("other error");  
264:     break;  
265:    default:  
266:     Serial.println("unknown error");  
267:   }  
268:  }
```
