LIXIE for ARDUINO CHANGELOG:

# 1/4/17:
**- Started changelog, should have done this sooner!**

**- Added max_power(volts,milliamps) function:**

I discovered that FastLED has an option to limit global strip brightness based on the max wattage you'd like to consume. This is amazing! By default, the Lixie library will limit the current consumption to 5W, or 1A @ 5V. Under normal use, each digit will only consume a maximum ~120mA by having two LEDs lighting a digit with full white. You could run 8 digits without hitting the 1A cap.
		
  But some people might want to make the displays flash a color using all LEDs, as in the end of a countdown clock or IFTTT notifications. To protect your power supply (probably USB) from being overloaded, this default 5W cap is placed when lix.begin() is called. To change the maximum consumption allowed, enter your power supply specs into this new function:

    lix.max_power(volts,milliamps);

Be sure to leave some modest headroom for other things like the microcontroller doing all the work!