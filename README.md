Tama P1 Emulator for Flipper Zero (now in portrait mode*!)
=========================================================

This is a tama P1 Emulator app for Flipper Zero, based on [TamaLIB](https://github.com/jcrona/tamalib/).

**icons still in landscape mode*

How to play
-----------
Create a `tama_p1` folder in your microSD card. Use a search engine to find the Tamagotchi ROM. There is a file named `tama.b`. 
Rename this to `rom.bin`. 

*Controls are the same as the landscape version, but turned 90 degrees.*
- Left button is A.
- Down or OK is B. 
- Right button is C. 
- Holding the Up button functions the same as press both A and C, which mutes the volume. 
- Hold the Back button to save and exit.


Building
--------
Move this folder to `applications_user/TAMA-P1`. 


Launching the app, directly from console to flipper: 
```
./fbt launch_app APPSRC=applications_user/TAMA-P1
```

Run the following to compile icons:
```
scripts/assets.py icons applications_user/TAMA-P1/icons applications_user/TAMA-P1/compiled
```

Note: you may also need to add `-Wno-unused-parameter` to `CCFLAGS` in
`site_cons/cc.scons` to suppress unused parameter errors in TamaLIB.

Debugging
---------
Using the serial script from [FlipperScripts](https://github.com/DroomOne/FlipperScripts/blob/main/serial_logger.py) 
it is easy to add direct logging after running the application: 

```
python .\serial_logger.py
```
```
./fbt launch_app APPSRC=applications\plugins\tama_p1;  python .\serial_logger.py
```
