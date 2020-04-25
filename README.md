
OSBeeWiFi ESP8266 Firmware 

Forked from: https://github.com/OpenSprinkler/OSBeeWiFi-Firmware

Updates:
=======
* (Dec 5) Release OSBeeWiFi firmware 1.0.0
* Blynk removed


Firmware Features:
=================

* Initial Connection to WiFi:

On first boot-up, the firmware starts in AP mode, creating a WiFi network named OSB_XXXXXX where XXXXXX is the last six digits of the MAC address. This is an open AP with no password. The LCD displays the AP name and a dot blinks quickly at about twice per second. Using your phone or computer to connect to this AP, then open a browser and type in

192.168.4.1

to access the AP homepage. If you use Android phone, it may warn you about 'No Internet Connection'. Simply click the checkbox to confirm.

Select (or manually type in) the desired SSID, password, and (optionally) Blynk's authorization token (refer to the instructions above). If you don't want to input the Blynk token, you can leave it empty for now. Then click 'Submit'. Wait for 15 to 30 seconds for the device to connect to your router. If successful, it will display the local IP address with further instructions.


* Reset to Factory Default:

At any time, you can press and hold the pushbutton for at least 8 seconds, until the LCD displays the 'Resetting' message. At this point, the device will perform factory reset and restart in AP mode.

* Using the Built-in Web Interface:

Open a browser and type in the device's local IP address. The build-in web interface allows you to:

  - Check the device status
  - Change settings
  - Trigger zone actions
  - Set programs and preview programs
  - Manually run a program
  - View log
  - Reboot the device
  - Update firmware
  
Certain operations require a device key, which by default is

opendoor

In Settings, you can change the time zone, device name, zone names, Blynk token, HTTP port, and device key etc. Changing certain options (such as token, HTTP port) requires a reboot.



Update Firmware:
===============

The current firmware version is displayed at the homepage. When a new firmware becomes available, you can click on the 'Update' button next to the firmware version to upload the new firmware.

If the update ever fails, power cycle (unplug power and plug back power) the device and try again. If it still doesn't work, you can update firmware through the USB port (see instructions above).


Notes about Modifying Firmware:
===============
You can change the firmware code to add new features and follow the instructions above to compile and upload. Note that the built-in user interface embeds HTML files to the firmware source code. To modify the HTML files (so that you can change how the webpages are rendered), go to the html/ subfolder, which contains the original HTML files. Make any changes necessary, and use the html2raw tool to convert these HTML files into program memory strings (which are saved in htmls.h). Every time you make changes to the HTML files, you must re-run html2raw in the html folder to re-generate the program memory strings.
