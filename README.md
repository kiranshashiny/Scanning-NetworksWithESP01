# Scanning-NetworksWithESP01
ESP01 is used to scan WiFi Routers


The link that was used to program the ESP 01 after searching several web sites:

https://github.com/kiranshashiny/Scanning-NetworksWithESP01.git

and the USB to RS232 converter

https://www.amazon.in/s/ref=nb_sb_ss_c_1_3?url=search-alias%3Dindustrial&field-keywords=usb+to+serial+converter&sprefix=USB%2Cindustrial%2C594&crid=1N2T4LFHH5R4X


<img width="645" alt="screen shot 2017-12-25 at 11 12 05 am" src="https://user-images.githubusercontent.com/14288989/34333605-9a5594d0-e964-11e7-9a59-53803b63e241.png">


I did not connect the Reset buttons on the GPIO0 and 3.3V of the RS232 interface.
Also I did not use the 10K Pull up resistor.

When I got the error messages as shown below - I pulled out the RS232 USB Interface and inserted it back into the USB slot.
This acted like a Reset switch of sorts.
and sometimes I got a 'Incomplete upload' and I had to retry it again and again - until it worked.
( at most 2 attempts)
```
Sketch uses 226,681 bytes (52%) of program storage space. Maximum is 434,160 bytes.
Global variables use 31,856 bytes (38%) of dynamic memory, leaving 50,064 bytes for local variables. Maximum is 81,920 bytes.
warning: espcomm_sync failed
error: espcomm_open failed
error: espcomm_upload_mem failed
error: espcomm_upload_mem failed

```


The proper fix was done as suggested in the diagram above and adding the RESET button fixed the upload issues.

A 3.3v regulator was added to 12V power supply to get me the required DC output to ESP01.



Another interesting link for fixing reset problems in ESP

https://iotbytes.wordpress.com/3-3v-power-supply-for-esp-8266/
