[<img width="171" alt="kofi_s_tag_dark" src="https://github.com/3DPrintDemon/Demon_KLIPPER_Essentials/assets/122202359/6538fcbf-b866-4e33-81c6-f9c95428bca4">](https://ko-fi.com/3dprintdemon)

## Don't forget if you like & use this project you can buy me a beer/coffee to say thanks. [https://ko-fi.com/3dprintdemon](https://ko-fi.com/3dprintdemon)

# Demon_KLIPPER_Essentials
Devilishly Good!
# v2.3 Rewritten, now your printer just got even smarter!

This macro pack will run on any compatible printer, giving you an amazingly adaptive & efforless feeling to using your machine!

Plus a copy/paste how to install Klipper from scratch guide, which is jammed full of extras & advanced features!

Also included is the custom boot screen image & 3DPRintDemon Keyring.stl

Here you'll find all the info you'll need to get Klipper running on your printer. Follow the instructions in the install guide if you are starting from scratch. Links & credits for sources have been given where possible, if I've forgotten or missed any let me know & I can update things as needed.

The .cfg files have been written & tested by myself. I run them on my own machines. The goal of these macros has always been to be as automated and unobtrusive as possible! No clutter, no million macro buttons, no endless choices & commands. This is a hit print & know the printer does the rest system!  

Start_End_Print.cfg has all you need to get your Klipper printer prepared for a print correctly with automatically adaptive modes that will set the printer up for your print by itself! All you need do aside from a few simple setup steps is check & maybe edit the variables section in the file to your liking. 
****************************************************************************************************************************

# This macro relies on you setting the correct filament type in your slicer! BE SURE YOU DO THIS!

# FEATURES: 

### **Demon Start End Print**

- The printer knows what filament you sliced your print for!

- You can now choose 2 different flow rates for each filament that are automatically selected depending on if you're using a small layer height for fine detail prints, or a large layer height to get stuff done quick for that filament! - LOVE THIS! 

- Pressure Advance & Smooth Time values for each filament, each can will be applied automatically, if the filament type is unrecognised the default stored value is used.

- Pre print filament runout check 

- Fast & adaptive Nozzle Preheat, values for each of the 5 filament presets. If the filament you're using is not on the list then the macro falls back on reading the file temps & makes a decision from there.

- Fully conditional homing, don't home again if you don't have to!

- If you have a chamber or printer enclosure with a cooling fan then there are settings for when the fan comes on for each filament to help maintain the correct temperature!

- Store 5 Meshes, one for each filament type. Each will be called automatically for the correct filament! Then if the filament type is not recognised the macro will fall back on reading the file temps & makes a decision from there.

- Automatically applied high temperature expansion offset for ASA & ABS filaments with a bed-saver safeguard! You set the offset to use. This will only allow small adjustments so can't dig trenches into your bed! Range of -0.1mm to +0.1mm is available. Anything outside this range causes an Emergency Stop! Offset adjustment feature can be switched on/off. USE WITH CARE!

- PETG Anti-Squish with bed-saver safeguard! This allows a positive Z offset to all PETG prints automatically to reduce the first layer squish. Range 0.00 to +0.1mm. Anything outside this range causes an Emergency Stop! Offset adjustment feature can be switched on/off. USE WITH CARE!

- Filaments have Heat Soak timers that are now controlled by either enclosure temp sensor readings, or timers. You choose! Timers are default if you don't have an enclosure or sensor.

- Support for 5 stepper driver systems with Z-Tilt option

- Customise your purge line! Choose where to start & which axis to purge along! X or Y! It automatically adapts to your file's extrusion height & width!



### **Demon User Settings**

- This file contains all the 'Variables' available for the Demon Macros, open & edit one single file! No need to trawl through macros!


### **Demon General Instructions**

- Full instructions!
  

### **Demon Prepare Menu**    

- Add a whole new Prepare menu to your Klipperscreen! Gives you a single click ReadyUp feature, plus Prepare to load/unload.

  *Not available on the Sovol own brand Klipper screen unit


### **Demon_Essentials**

- Easy and automatic single button press Macros to help you setup your printer.

- Pressure_Advance_Test_Mode.

- Stepper_Buzz_Cycle.

- Printer_PID_Tune.

- Probe_Z_Calibrate.

- Auto_Shaper_X and Y.

### **VERSION CHECKER!**
- The macros now check you are using the correct version files!


****************************************************************************************************************************
# IF YOU RAN V1.0-V2.2 BE SURE TO UPDATE YOUR SLICER'S START GCODE AS PER V2.3 FILE OR NEW FEATURES WONT WORK!
****************************************************************************************************************************


# INSTALL

Copy the files here into a folder called `Demon_KLIPPER_Essentials` in your config folder on your printer. 

Then, paste into your printer.cfg
```
[include ./Demon_KLIPPER_Essentials/*.cfg]
```

This will include all files in a folder called Demon_KLIPPER_Essentials in your `~/config` folder.

Or you can use...

```
git clone https://github.com/3DPrintDemon/Demon_KLIPPER_Essentials.git
```

Then, paste into your printer.cfg
```
[include ./Demon_KLIPPER_Essentials/*.cfg]
```

You can even be notified of updates by editing your `moonraker.conf` file with...
```
[update_manager Demon_KLIPPER_Essentials]
type: git_repo
origin: https://github.com/3DPrintDemon/Demon_KLIPPER_Essentials.git
path: ~/printer_data/config/Demon_KLIPPER_Essentials
primary_branch: main
is_system_service: False
managed_services: klipper
```

This will bring these files into your system, & give you update options, be sure to comment out & NOT delete your current START & END PRINT Macros just yet!


# SETUP

open & READ through the `demon_general_instructions.cfg` file!!!

You must also build a new high temperature meshes with the bed temperature 
- default` (to use with PLA)
- ASA
- ABS
- PETG
- TPU

Then Head over to here & download the companion Heat_Soak_Sovol.cfg to use with this START_PRINT Macro
https://github.com/3DPrintDemon/Non_Blocking_Wait_Sovol/releases/tag/Heat_Soak_Timers_V1.0

If you don’t want or need you can comment out the `_HEAT_WAIT` lines
Or if you don’t want the LED commands you can comment them out in that file but still have the Heat_Soak timers.

Lastly to get the LED functionality you have to go into the `HEAT_SOAK_SOVOL.cfg` file & name your printer’s LED PIN so the Macro can control it.
If you don’t do this it WONT WORK. They are set to my_led by default.

Now set your `Demon_User_Settings` & happy printing!

# WANT MORE...??
Whats that I hear you cry, you want more?! Ok I got you covered!

How about fully automated power on/off control with auto cool down & shutdown after a print finishes?! Plus have full control even after Klipper is in shutdown! What is this black magic?!!!

Find out here!

https://github.com/3DPrintDemon/BTT-Relay-v1.2-Moonraker_INSTANT_Power-On-Button

If thats not enough how about creating your very own online auto updating backup of all your config files here on Github in your own private repo?!

https://github.com/3DPrintDemon/Auto_Backup_Your_Klipper_Printer



# IF YOU RAN V1.0-V2.2 BE SURE TO UPDATE YOUR SLICER'S START GCODE AS PER V2.2 FILE OR NEW FEATURES WONT WORK!



****************************************************************************************************************************


Watch: https://youtu.be/KZaZbgVa_8Q



[<img width="171" alt="kofi_s_tag_dark" src="https://github.com/3DPrintDemon/Demon_KLIPPER_Essentials/assets/122202359/6538fcbf-b866-4e33-81c6-f9c95428bca4">](https://ko-fi.com/3dprintdemon)



