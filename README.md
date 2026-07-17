# ZPS_ZIgbee_GPS_Node
A Zigbee based WSN node built using ESP32-C6 and NEO-7M GPS modules

If you tried to make a project with zigbee outside the built-in examples from arduino ide or esp ide, you know it is frustratingly cumbersome. I went through it and hence sharing some of my experience so you don't have to go through same.
__________________________________________________________________________________________________________
**This project makes use of ESP32-C6-Devkitc-1-N8 modules as the coordinator and the end device nodes. To flash this boards I used ESP IDE with ESP IDF version 5.3.2 (For some reason they removed some of the zigbee stack featureset in later versions). I faced many compilation issue while doing this on Windows, so eventually installed Ubuntu 24.04.4 and there downloaded ESP IDF 5.3.2, then this worked. So if you are facing errors while compiling, the IDF version could be the issue.**
______________________________________________________________________________________________________
**Things to consider**
1. Before clicking build, make sure you have chosen the correct board. It is best practice to make sure your com port detecs the chip automatically through the inbuilt detect option while you       select the board.
2. After you have used this code, update the `Cmakelists.txt` within the main folder with the name of the .c files you are saving as.
   It should be like this:
  ```cmake
	idf_component_register(
	  SRCS 
		  "coordinator.c"
		  "gps_reader.c"
      INCLUDE_DIRS 
      	"."
	)
  ```
3. While flashing, before you connect the usb cable to the ESP board, press and hold the boot button, connect the cable then release, makes the board enter boot mode.
4. If you have already tried flashing other zigbee firmwares before and want to start over again, you should erase the chip's old firmware before uploading new, cause even if you change             firmware, the zigbee defined pan id and address remains unchanged. I like to do it by going in `eim > Open Dashboard > Open IDF Terminal (1st Option)` then type `esptool.py --chip YOUR_CHIP -    -  port YOUR_PORT erase_flash`.
   For Windows, the com port would be like `COM5`, for Linux it would be of the format `/dev/ttyUSB0`
