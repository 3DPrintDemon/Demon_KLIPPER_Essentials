# Demon_Essentials
Devilishly Good!

Klipper .cfg files aimed at Sovol Printers, plus a copy/paste install guide

Here you'll find all the info you'll need to get Klipper running on your Sovol (and other!) printers, follow the instructions in the install guide if you are starting from scratch. Links & credits for sources have been given where possible, if I've forgotten or missed any let me know & I can update things as needed.

The .cfg files have been written & tested by myself. I run them on my own machines.

Start_End_Print.cfg has all you need to get your Klipper printer prepared for a print correctly with automatically adaptive modes that will set the printer up for your print by itself! All you need do aside from a few simple setup steps is check & maybe edit the variables section in the file to your liking. 


**Demon_Start_End_Print FEATURES:**

ADAPTIVE Nozzle Pre Heat stage - automatically set a chosen warmup temperature for both high & low temperature filament printing!

ADAPTIVE Bed Heating Stage & Mesh Selection stage - while automatically heating the bed the printer will select the correct bed level mesh for the temperature range!

SELECTABLE Bed Heat Soak Times - these are also adaptive & will be automatically selected, you just choose the time.

ADAPTIVE First Layer Height Purge Lines - the START_PRINT purges line will now perfectly match the height of your first layer of your print every time!

MACRO VARIABLES - these are used to configure all the above functions plus easily letting you set your chosen starting flow rate.


**Demon_Essentials FETAURES:**

Easy and automatic sinlge button press Macros to help you setup your printer.

Pressure_Advance_Test_Mode.

Stepper_Buzz_Cycle.

Printer_PID_Tune.

Probe_Z_Calibrate.

Auto_Shaper_X and Y.





**Demon_Start_End_Print Setup steps…..**
THERE ARE INSTRUCTIONS IN THE FILE ITSELF!

Copy/paste the 3 slicer lines into Prusaslicer’s Start_GCODE window. You will have to modify them for other slicers.
You MUST do this or the START_PRINT Gcode WILL NOT WORK! 

You must also build a new high temperature mesh with the bed temperature OVER 90ºc & store it with the name “HOT”. 
DO NOT OVERWRITE YOUR DEFAULT MESH!

Then Head over to here & download the companion Heat_Soak_Sovol.cfg to use with this START_PRINT Macro
https://github.com/3DPrintDemon/Non_Blocking_Wait_Sovol/releases/tag/Heat_Soak_Timers_V1.0

If you don’t want or need you can comment out the _HEAT_WAIT lines
Or if you don’t want the LED commands you can comment them out in that file but still have the Heat_Soak timers.

If you have a 5 stepper driver printer, like an SV07 be sure to uncomment to enable `Z_TILT_ADJUST` gantry levelling!

Then, paste into your printer.cfg

`[include demon_essentials.cfg]`

`[include Demon_start_end_print.cfg]`

`[include Heat_Soak_Sovol.cfg]`

This will bring these files into your system, be sure to comment out & NOT delete your current START & END PRINT Macros!

Now set your `START_VARIABLES` & happy printing!

Lastly to get the LED functionality you have to go into the `HEAT_SOAK_SOVOL.cfg` file & name your printer’s LED PIN so the Macro can control it.
If you don’t do this it WONT WORK. They are set to my_led by default.




