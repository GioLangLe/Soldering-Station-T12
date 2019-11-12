# Soldering Station T12 @ STC15F2K60S2-28I-LQFP32
Hey all, 

- My old product is damaged, I want something stronger, faster, etc ....

More details about the product: Video update

  - T12 with a capacity of 72W, works most strongly at 24V> = 3A. It only takes about 5 ~ 7 seconds. You can check it out for yourself. When you came back it was a few times stronger: D: lol:
  - Support Leddot or LCD Oled
  
Current firmware: power-on password lock, password-lock temperature, 3 types of soldering iron parameters to save and recall functions (should be enough to be confused), double-click and click Shortcuts (function included one strong temperature button, turn off one button, sleep one button, three temperature switches, head switch, etc.), set the sensitivity of the vibration switch, adjust the volume and adjust the frequency, adjust the time Sleep More than 20 personalized settings, such as adjusting shutdown time, screen off automatically, low voltage alarm, etc., each function can be selected to close and open. There are many options for screensaver display mode (temperature display only, display clock, display logo, etc.)
 
Normal users can directly use the default settings, no need to set directly to use, to adjust the default restore value, easy to use. Press and hold for 3 seconds, then you can enter the menu after listening and you can set the interface without any instructions.

I do not have the correct device to adjust the temperature yet. So sad. But around 300o  Celsius, it's too strong to melt everything.

Why it is STC and not STM, because it is quite difficult to order it plus MCP602 (AD822). : lol:


Because the thermocouple parameters of different welding irons vary by even several tens of degrees, the temperature adjustment parameters of the three soldering irons built into the soldering station can be transferred. exchange at any time. - Xi'an head, soldering iron head No. 3 - original head, users can also correct the parameters according to the actual situation.

Temperature increases rapidly, good temperature recovery properties, good or bad temperature index, mainly depends on heating capacity when the temperature is within 30 degrees of the set temperature. Our commitment is like a soldering station with a temperature better than this one (within a tolerance of 4%)

Can replace LM7805 with LM2596T-5V, it will be more cool.

Hakko T12 Soldering Tips
The Hakko T12 soldering tips are very convenient tools: they are heating extremely fast and have a sensor inside that allows to keep the temperature very stable. It is a big pleasure to use such a amazing tool. The tips require just three wires: plus, ground and earth. The heating element inside the tip is connected consequently with the thermocouple allowing to decrease the required wires. It makes the cable very flexible and light weight.

To use the T12 tips you may need to order a handle. The one I would like to recommend is a FX9501. The problem is a connector. To connect the handle to the controller you can replace the standard connector with some kind of aviation plug which can be ordered on eBay, for example. GX12-5 is a good choice. The FX-9501 handle has a three-wires cable.

To install the temperature sensor (thermistor) inside the handle, you may need to replace the cable with the five-wires one.

When connecting the handle to the GX12-5 plug you can use the folowing reference of the plug pinout.

Also you can order Chinese soldering kit like shown on the picture below and use another handle in this project. This kit contains tilt switch and thermistor.

Flash The Firmware to the Controller

To flash rebuilt firmware to the controller the STC programmer and TTL utility are required.
Tune the Controller
The external thermo-couple required during this procedure.

In the controller schematics you can see two 500k potentiometer R5 that tunes the operation amplifier to get the expected temperature readings at controller pin PA4 pins of BluePill board. You can use different operating amplifier, so this potentiometer is increasing the controller flexibility.

The potentiometer should be tuned at least once you created the controller. The main idea is that the controller reads the voltage from the thermo-couple through the ADC and gets some integer data in the interval 0-4095 depending on the voltage on its pin. The near the voltage to 3.3v the near the readings to the 4095. The potentiometer should be tuned so when the iron temperature become 450 Centegrees, the ADC reading should be about 4000.

To simplify controller tuning procedure, the tune mode is implemented in the controller. This mode can be activated from the system menu item 'tune iron'. When the tune mode is activated, the controller powers on the iron and displays on the screen applied power (in percents) and the gauge of the current temperature readings. The gauge has a label '450'. When the gauge reaches this label, the iron temperature should be 450 degrees of Celsius.

Connect external thermo-couple to the iton tip and enter the tune procedure. The iron should start heating. Rotate the encoder to change the supplied power to the iron. Adjust the power manually to keep the iron temperature as near to 450 Celsius as possible. Then tune the 500k potentiometer to shift gauge bar on the display left or right. Adjust the potentiometer so the bar would be as near to the label as possible. Then press the encoder handle for about 2 seconds to turn the iron off and finish the procedure. It is recommended to use the thick tip that produce the highest voltage when performing the tune procedure. For example, T12-K, T12-D52 or so.

Note:To perform tuning procedure more precisely, apply a solder drop to the contact between the thermo-couple and the soldering tip rod.

- Sorry for bad english.
