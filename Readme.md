# ESP-NOW network + WiFi gateway to the Internet

The objective of this mini-project is to illustrate a communication based on the (connectionless) ESP-NOW protocol between a set of ESP32 senders and an ESP32 receiver, while configuring the receiver as a gateway to the Internet by connecting it to a WiFi router.

![Scheme of implementation][picture]

This mini-project was born from the observation of an erroneous
implementation on the following tutorial, published by Rui and Sara on
Random Nerd Tutorials:

[ESP32: ESP-NOW Web Server Sensor Dashboard (ESP-NOW + Wi-Fi)][tutorial]

This observation led me to open a [discussion][discussion] on the RNT Lab forum to get the opinion of interested readers. And I'd especially like to thank Lee and Steve for taking the time to discuss the issue with me. We were finally able to identify what was wrong.

The solution was initially published on the Espressif forum by **ardcp32**, which I thank in passing, and which [you will find here][solution].

This mini-project is therefore intended to illustrate the right way to proceed for all readers of Random Nerd Tutorials.

You'll find here the code to be implemented on all ESP-NOW sending nodes, as well as that of the ESP-NOW receiving gateway, which is simultaneously connected to the Internet through a WiFi router.

Note that for this to work, each sender must use the same radio channel as the WiFi router. It is hardcoded in my example (on channel 6), but if your router is configured to automatically switch to the least congested channel, you will need to add a routine to scan the available networks and identify the channel imposed by your router.

[picture]:    assets/esp-now-gw-wifi-router.jpg
[tutorial]:   https://randomnerdtutorials.com/esp32-esp-now-wi-fi-web-server/
[discussion]: https://rntlab.com/question/esp-now-gateway-wifi_mode_sta-with-a-wifi-router/
[solution]:   https://www.esp32.com/viewtopic.php?f=19&t=12992#p51338