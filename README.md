# temperature-measurement-on-solid-fuel-boiler
-> This project is for people who forget to add coal or wood to the boiler.  The measurement is done using a K-type thermocouple together with a MAX6675 converter and a lolin ESP8266 node MCU( I used this board as it was lying around at home). The thermocouple is attached to the flue pipe from the boiler from which it takes the temperature. 

-> Using all the above mentioned components, I wrote code that can plot the temperature from the boiler into a graph on a webserver that runs on the ESP8266.

![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/bf37de21-0ded-442d-b5d7-f1c64e91679e)

-> In winter I will add to the code a function to send messages to WhatsApp, where the user will receive messages about whether the temperature of the flue has dropped below the threshold where the fire is still burning or has already burned out. The messaging on WhatsApp will be done by CallmeBot.  I'll add this in winter, because now there are no temperature conditions in the Czech Republic to stay in the house with a melted boiler and outside temperature.

-> To use the max6675 converter it is necessary to use the <max6675.h> library from adafruit.com and then connect the pins to the board correctly according to the datasheet.
I found the datasheet on AnalogDevices website and also a link to a similar project where they used the same components. According to these two sites I connected the converter to the board.

![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/162debc5-4f90-4cc9-aafc-4749934ece44) [1]

Wire  connections between esp8266 and MAX6675
![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/f80d2c17-db7b-4b4b-a319-b376f1db7820) [2]

Table for connections between esp8266 and MAX6675
![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/057ee5a3-b1b1-4e93-b1ff-0e5a15c52e3e) [2]


-> Here are the links: 

https://www.analog.com/media/en/technical-documentation/data-sheets/MAX6675.pdf

https://microcontrollerslab.com/k-type-thermocouple-max6675-amplifier-esp8266-nodemcu/

-> I connected the device to WiFi using the classic library <ESP8266WiFi.h> using WiFi ssid and password. 

-> I assigned a name to the webserver using the mDNS library <ESP8266mDNS.h> for ESP boards or you can use an IP address, but that's impractical and you forget it after a while. MDNS will only work at your local network. It can be accessed by PC, Apple devices or any davice which has Android version 12.0.. 

-> The graph is getting new temperature reading each 5 seconds. 

![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/eea99f87-8b96-41a6-ab8d-2b7e7338d077)

-> used components: 
1. Node MCU Lolin ESP8266
2. K-type thermocouple with MAX6675 convertor
3. Home made PCB drawn with marker 
4. 100uF capacitor for power supliing
5. Classic smartphone charger
6. Terminal strip
7. Two line wire cable
8. Printed box for pcb with all components
9. screws on the box and hammered into the wall
10. Old USB cable for power supliing
11. female pins for plugin the ESP desk 


-> the final product fell out as follows:

![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/4b186a38-8553-4920-abc8-1077adb0c587)  ![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/ae10455a-80eb-4b9a-8482-865dd9de51a4)

on one PCB I put together a board with ESP8266 and thermocouple with converter together with all necessary capacitors and terminals and I put it all in a printed box.

![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/5f6e5b81-1c08-4322-9cc7-4857ba716f66) 

![image](https://github.com/DominikTomasek/temperature-measurement-on-solid-fuel-boiler/assets/55549002/93998a32-1774-4662-b9bc-d07d451b7787)

->resources used for this project:

1.https://www.analog.com/media/en/technical-documentation/data-sheets/MAX6675.pdf

2.https://microcontrollerslab.com/k-type-thermocouple-max6675-amplifier-esp8266-nodemcu/

3.https://www.thingiverse.com/thing:4689602
