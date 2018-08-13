# Updating HX3.5 with HX3.5 Editor

**Using FTDI device connection**

![Finalize Window](Editor508_finalize.png)

### Connection

HX3.5 Editor connects to HX3.5 mainboard either through bi-directional MIDI 
connection (IN/OUT) using a third-party MIDI adaptor, by MIDI over USB using a 
USB connection or by our FTDI serial adaptor cable. Also, any FTDI device with 
FT232 chip as our FTDI serial adaptor board may be used. Power up HX3.5, Open 
HX3.5 Editor application and click on Connect. A dialog window will appear, which 
asks for the MIDI device to use. 
See [HX3.5 Editor manual](http://wiki.keyboardpartner.de/index.php?title=HX3.5_Editor)
for further details.

### FTDI connection

Attach USB-to-serial adaptor cable FT232R-5V to any PC USB port and HX3.5 6-pin 
header PL19, black wire (BK) facing to black header PL17. On first install, 
Windows will install FTDI drivers automatically (Win XP needs manual FTDI driver 
installation). On Connect, Check "Use FTDI devive instead of MIDI" box. Select 
FT232R entry and click OK. HX3.5 Editor will wait for communication established 
and reads all parameters from HX3.5 mainboard. Log window will show all 
activities as well as (plain text) answers from HX3.5 mainboard. 

For updates, entering extended licences or changing Scan Driver from MIDI to 
FatarScan2 or Scan16/61, click on HX3.5 Update/Finalize. A window will open 
showing active board licences and serial number. Make sure at least Organ 
Licence "LED" is lit - otherwise licence number is corrupted and must be entered 
here (see back of board or obtain new licence number from KeyboardPartner).

### Scan Drivers Update

Select "Scan Driver file" from drop-down menu via FTDI 
device. HX3.5 Editor will prompt for a Scan Driver .DAT file (either 
scanmidi.DAT or scanfatr.DAT at this time). Scan Drivers can be found in UPDATE 
directories resp. ZIP files.

### FPGA and Firmware Updates

Analog to Scan Driver updates, individual parts may be updated by file upload 
also. Please note: File transfer of FPGA 
(sound engine) configuration may take up to 4 minutes using the FTDI serial 
cable. For a complete update, each file must be uploaded individually! For 
experienced users: You may skip some files if their creation date is not 
different from those already installed.

### Extended Licences

Make sure that green Organ Licence "LED" is already lit. To install an Extended 
Licence, enter number in Extended Licence text field and click Send 
Licences/Name.

