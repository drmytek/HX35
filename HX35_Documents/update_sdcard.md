# Updating HX3.5 using SD Card

Firmware updates and Setup scripts (.INI files) may be executed from SD card. An 
appropriate SD card adaptor is available from KeyboardPartner. Attach SD card 
adaptor cable to HX3.5 board connector PL17. 

* Unzip and copy all files from appropriate ZIP file "UPDATE" to an empty SD or SDHC card 
* Make sure that all files are located 
in the card's root directory 
* Insert SD card in HX3.5 card adaptor and power up 

Update will start automatically on power-on if a file called "autorun.ini" is 
present on SD card. Once the update is completed, this file will be renamed to 
"_autorun.ini" to prevent further obsolete updates.

The HX3.5 Editor application is also able to trigger updates from SD Card (in 
Update/Finalize Window) -- see [HX3.5 Editor manual](http://wiki.keyboardpartner.de/index.php?title=HX3.5_Editor)
for details.

Firmware updates from SD card are basically controlled by "Setup Scripts" (.INI files) 
executed from SD card. Scripts consist of a series of text commands; they can 
invoke a firmware file load, but also can change a series of parameters. On devices 
equipped with a MenuPanel, select a script file by turning the encoder knob; to 
start the script, press and hold encoder knob for at least 2 seconds until “Run 
Setup file” message appears. 

