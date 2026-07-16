# ZPS_ZIgbee_GPS_Comms
A Zigbee based WSN node built using ESP32-C6 and NEO-7M GPS modules

If you tried to make a project with zigbee outside the built-in examples from arduino ide or esp ide, you know it is frustratingly cumbersome. I went through it and hence sharing some of my experience so you don't have to go through same.
__________________________________________________________________________________________________________
**This project makes use of ESP32-C6-Devkitc-1-N8 modules as the coordinator and the end device nodes. To flash this boards I used ESP IDE with ESP IDF version 5.3.2 (For some reason they removed some of the zigbee stack featureset in later versions). I faced many compilation issue while doing this on Windows, so eventually installed Ubuntu 24.04.4 and there downloaded ESP IDF 5.3.2, then this worked. So if you are facing errors while compiling, the IDF version could be the issue.**
______________________________________________________________________________________________________
