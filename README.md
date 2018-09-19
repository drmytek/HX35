# HX3.5

![HX35 Board](https://github.com/keyboardpartner/HX35/blob/master/HX35_k.JPG)

## Firmware and Docs for HX3 mk5

**IMPORTANT: Be sure to extract all ZIP files to a local hard disk folder. Update 
will fail if started directly from ZIP window.**

Updates for HX3.5 consist of several parts:

Please download the ZIP file dedicated for your particular product 
configuration. Unzip and copy all files from appropriate ZIP file "UPDATE" to a 
local folder on your harddisk. 

Updates are possible by one of the following methods:

* via [HX3.5 Editor with MIDI connection](http://wiki.keyboardpartner.de/index.php?title=HX3.5_Update_by_MIDI) (Windows operating system required, all devices)
* via [HX3.5 Editor with FTDI USB/serial adaptor cable connection](http://wiki.keyboardpartner.de/index.php?title=HX3.5_Update_by_FTDI_or_Extension_Board_mk4) (Windows operating system and access to board connectors required)
* via [HX3.5 Editor with old Extension Board mk4](http://wiki.keyboardpartner.de/index.php?title=HX3.5_Update_by_FTDI_or_Extension_Board_mk4#Extension_Board_mk4_connection) (Windows operating system required)
* via [SD Card and SD Card slot adaptor](http://wiki.keyboardpartner.de/index.php?title=HX3.5_SD_Card_Usage), available separately (access to board connectors required)
 
Parts to be updated from previous version are mentioned in headline.

### Changelog

<b>09/19/2018</b> Firmware #5.105, HX3.5 Editor #5.105, Scan Driver 5x.16

* Firmware: Bugfix Preset/Live and Preset/Preset change
* Firmware: Will not forget presets and voices when updating
* Firmware: Bugfix "Split Mode not stored to Overall Presets"
* Scan Driver: Split mode handling improved
* Scan Driver: Bugfix non-working pedals on "Lower to Upper Split"
* HX3.5 Editor: Assignment Dropdown List Bugfix
* HX3.5 Editor: Changes for 16 KByte "preset.dat" file

For updates from #5.103 and below to #5.105 select "Firmware/EEPROM" and "Scan 
Driver File" in HX3.5 Editor's Update/Finalize Window and Execute "config.ini" 
from Editor. SD card updates will handle this automatically.

Hx3.5 will create a "preset.dat" file (button "Get & Save Preset Block" in 
"Advanced" page) if connected by FTDI. This file contains all preset settings in 
binary form. It may be uploaded by menu in Update/Finalize window or copied to 
an SD card. If HX3.5 finds this file on a firmware update, it will be loaded 
into preset memory.

Preset structure will not change in future, so this file may also be used as a backup.

<b>09/12/2018</b> Firmware #5.104 BETA, HX3.5 Editor #5.104, Scan Driver 5x.15

* Known Bug: Preset/Preset change 
* HX3.5 Editor: "Menu Enables" order fixed
* HX3.5 Editor: Added update entry "Firmware only" in Update/Finalize Window
* Firmware: Switching of H100/B2 Percussion fixed
* Firmware: "Sync Voices with Presets" enabled on UHL instruments
* Scan Driver: Bugfix MIDI channel assignment (was not able to receive on MIDI channels other than 1/2/3)

For updates to #5.104 select "Firmware/EEPROM" and "Scan Driver File" in HX3.5 
Editor's Update/Finalize Window and Execute "config.ini" from Editor. SD card 
updates will handle this automatically.

<b>09/07/2018</b> Firmware #5.102, HX3.5 Editor #5.100, DSP #1.04

* HX3.5 Editor: New virtual organ panel with tabs and drawbars; should also work with older HX3.5 firmwares
* HX3.5 Editor: Will automatically start DreamDFU utility for DSP updates
* HX3.5 Editor: Added Backup support
* Firmware: Bugfix KeyB Duo MIDI CC set, Vibknob/MIDI to Panel16 translation, Perc menu display
* Firmware: Fail-save EEPROM file programming, unified firmware, "config.ini" support
* Firmware: Bugfix Percussion did not sound on preset to live change
* Firmware: Bugfix Rotary setting not memorized
* Firmware: Added Support for reading binary Preset and Voice setting blocks (OEM only)
* DSP: GM synth will no longer sound on channels out of organ channel range (1 to 3). Only update DSP if the GM synth should not sound on channels 4 to 16.

From firmware 5.1 and up, there is only one firmware common for all devices 
(exception: MAG and UHL organs). Firmware is "personalized" to work on a 
particular device by running a "config_xxx" INI script ("config_xxx.ini") from editor or by 
using SD card after update is done. 

If using an SD card for update, a script called "config.ini" is run 
automatically after firmware update by "autorun.ini" (if present on card). 
"config.ini" is simply a renamed "config_xxx.ini" file.

**Please backup Licence Info before updating to #5.102!** Unfortunately, older 
firmwares had a data offset bug which did not retain licence information and 
board defaults. When updating to #5.102, execute the "factory_xxx.ini" script 
dedicated for your board application from **HX3.5 Editor's Finalize** window or 
run "factory.ini" on SD card from HX3.5 Script Menu.


<b>08/30/2018</b> Firmware #5.096, HX3.5 Editor #5.095

* Firmware: Bugfix "Bass Rotor won't stop completely"
* Firmware: Bugfix "KeyB (Duo) MIDI CC interpreter not working"
* HX3.5 Editor: Added Button "Create INI Script", creates INI setup file with all current parameters
* HX3.5 Editor: Added Button "Run INI Script", runs INI setup file from Editor similar to running from SD card
* Added INI Setup Scripts for manual full update via DisplayPanel menu (update.ini), forced EEPROM rewrite in case parameters are corrupted (eeprupd.ini), 
and manual start DSP update in DFU mode, equivalent to HX3.5 Editor's "Start DFU" button (startdfu.ini)

<b>08/25/2018</b> Firmware #5.093, HX3.5 Editor #5.09, DSP #01.03 

* Firmware: Bugfix Update by USB MIDI
* Firmware: Added 8 separate Scanner Vibrato programs for 8 basic organ models, leftmost "Phasing Mode" tab 0 selects WersiVoice (OFF) or B�hm Phasing Rotor (ON) 
* Firmware: improved PHR params
* DSP: Bugfix SysEx handling - important, otherwise MIDI communication with Editor will produce communication problems and timeout errors
* HX3.5 Editor: Added "Start DFU" DSP update by MIDI, added descriptions for WersiVoice/PHR, 8 Scanner Vibrato programs (Group Scan/Vib Progs)

<b>08/16/2018</b> Firmware #5.091, HX3.5 Editor 

* Bugfix: EEPROM init restauration after update or factory reset was faulty
* Changed INI scripts to properly setup System Inits
* Use new HX3.5 Editor to update firmware. Will always update EEPROM if firmware update by FTDI or MIDI is selected from drop-down menu.

Important: Please update firmware twice, otherwise Button Remaps may contain 
garbage. With update by FTDI or MIDI using HX3.5 Editor, updating firmware 
is sufficient. "Finalize" with HX3.5 Editor or by SD card INI script after update.

<b>08/16/2018</b> Firmware #5.090, Scan Driver #14, HX3.5 Editor 

* Bugfix: GM Voice save to Overall Preset
* Bugfix: External Rotary control switch (Extension Board) 
* Bugfix: "randomly very low velocity sent" in Scan Driver 
* GM voices minor bugfix 
* HX3.5 Editor allows mapping of "extra" upper/lower/pedal voices #16..23 to any GM program number (see new 
"DSP/GM Setup" group). Click "Save Params as Default" after editing to activate new mapping.
* Lowered "Relative Organ Volume" param 1491 (see DSP/GM Setup Group in HX3.5 Editor) to 64 for better match to GM voices

Note: Disable Param 1497 (Sync Voice Numbers) in "System Inits" to enable GM 
Voice numbers saved in Overall Presets. From this FW and up, param 1497 will be disabled 
by default. **Do "Finalize" with HX3.5 Editor after update!**

<b>08/13/2018</b> Firmware #5.087, Scan Driver #12, DSP #01.02

* Mixture Drawbars will no longer sound on B3 and Combo Organ Models
* Phasing Rotor modulation enhanced 
* Sostenuto pedal changed from MIDI CC $42 to $45 (69 dec.) due to NI B4 Perc CC conflict. Without this update, HX3 Drawbar 
controller PERC ON will not work.
* DSP #01.02 will send CC $45 on Sostenuto pedal changes now
* MAG Organs only: Amp 122 volume will have a minimal amount

<b>07/30/2018</b> Firmware 5#.085, HX3.5 Editor

* Firmware, Scan Driver and FPGA update via MIDI, MIDI over USB or FTDI cable possible (needs one-time update via SD card)
* HX3.5 Editor version 5.08 also works with MIDI or MIDI over USB connection (no driver required on Windows PCs)
* Bugfix on Drawbar Mixture setup
* Bugfix Overall Preset Handling

<b>07/07/2018</b> Firmware #5.082, SD Card INI Scripts

* INI Script ReadLn bug fixed
* INI Scripts were corrupted (LF instead of CRLF)

<b>07/02/2018</b> Firmware #5.080, FPGA #09072018

* "Common Preset Save" Bug fixed
* Lower default leakage, was way too high 
* Issue with ENV_ENA Bits fixed, electronic gating was permanently on
* Various minor bugs fixed

Dateiliste
==========

Dokumente
---------

Schaltpl�ne und Audio-Routing-Blockdiagramme

Hilfsprogramme
--------------

"HX35_Editor_506": Editor/Parameter-Einstellung f�r HX3.5-Modul 
und HX3.5-Mainboard ab *Firmware 5.06* mit neuer Parameter-Struktur �ber 
serielle Schnittstelle mit FTDI-Kabel. Ben�tigt die im gleichen Ordner 
enthaltenen Dateien. F�hrt auch Updates und Finalisierung aus (Balfer). F�r 
Firmware ab 5.06 unbedingt HX35_Editor_506 benutzen! 

"HX35_Tapering": Editor f�r Lautst�rketabellen Hammond-Tapering (0 bis 3, B3 155 
bis B3 Recapped). Gegen�ber 3.4 angepasste Dateinamen und Speicherung der 
Einstellungen in INI-Datei.

"HX35_MIDIremote": Testprogramm f�r SEMPRA-MIDI-CC-Set mit allen �ber MIDI 
fernsteuerbaren Drawbars und Tabs. Testfunktion f�r SysEx-Daten. Nach dem Start 
angeschlossenes MIDI-Interface ausw�hlen. Ben�tigt ein USB-MIDI-Adapterkabel 
oder dgl. am PC.

"WavesetDesigner": Q&D-Editor f�r Wavesets. Nicht perfekt. Kann Generator-
Wavesets per Fouriersynthese erstellen, einfach per Schieberegler Oberton-
Anteile bestimmen.

Update-Dateien
--------------

Die f�r das Update n�tigen Dateien sind in den Ordnern HX35_SDCARD_XXX 
(XXX=OEM/Hersteller) enthalten. Achtung: Modul und Mainboard verwenden 
unterschiedliche FPGA-Konfigurationen!

Die Skripte werden vom AVR auf dem HX3.5-Modul direkt von SD-Karte abgespielt. 
Sie k�nnen Befehle zum Update des Flash-Speichers enthalten (Firmware, FPGA-
Konfiguration, ScanCores, Taperings, Generator-Wellenformen), aber auch 
nachtr�glich Parameter nach Wunsch �ndern. Die Skripte k�nnen �ber das HX3-
MenuPanel aufgerufen werden (nicht bei OEM-Modul-Firmware).

"autorun.ini": Skript zum automatischen Update. Kann auch Finalisierung 
durchf�hren (Lizenzen setzen). Ein Skript mit diesem Namen wird automatisch beim 
Booten ausgef�hrt und nach erfolgreichem Durchlauf in "_autorun.ini" umbenannt.

"update.ini": Skript zum Komplett-Update einschlie�lich FPGA und Firmware, wie "autorun.ini"

"waveupd.ini": Skript zum Update nur der Generator-Wellenformen

"coreupd.ini": Skript zum Update nur der ScanCore(s) und der Taperings

"taperupd.ini": Skript zum Update nur der Taperings

"scanupd.ini": Skript zum Update nur des Scan-Drivers (scan.dat), kann f�r MIDI oder Fatar sein

"scanmidi.ini": Skript zum Update nur des Scan-Drivers auf MIDI IN (hx_midi.dat)

"scanfatr.ini": Skript zum Update nur des Scan-Drivers auf FatarScan2 (hx_fatar.dat)


F�r ein Komplett-Update sind folgende Dateien n�tig:

"scan.dat": ScanCore (kann f�r MIDI oder Fatar sein), 

"taper1.dat"..."taper4.dat": Generator-Ausgangspegel und Manual Taperings (4 Sets), 

"waveset0.bin"..."waveset7.bin": Generator-Wellenformen (8 Sets mit je 8 Wellenformen),

"fir_coe.dat": FIR-Filterkoeffizienten f�r Leslie-Horn,

"firmware.bin": Firmware-Image f�r AVR, Flash-Inhalt,

"eeprom.bin": Firmware-Image f�r AVR, EEPROM-Inhalt

<b>08/25/2018</b> Firmware #5.093, HX3.5 Editor #5.09, DSP #01.03 

* Firmware: Bugfix Update by USB MIDI
* Firmware: Added 8 separate Scanner Vibrato programs for 8 basic organ models, leftmost "Phasing Mode" tab 0 selects WersiVoice (OFF) or B�hm Phasing Rotor (ON) 
* Firmware: improved PHR params
* DSP: Bugfix SysEx handling - important, otherwise MIDI communication with Editor will produce communication problems and timeout errors
* HX3.5 Editor: Added "Start DFU" DSP update by MIDI, added descriptions for WersiVoice/PHR, 8 Scanner Vibrato programs (Group Scan/Vib Progs)

<b>08/16/2018</b> Firmware #5.091, HX3.5 Editor 

* Bugfix: EEPROM init restauration after update or factory reset was faulty
* Changed INI scripts to properly setup System Inits
* Use new HX3.5 Editor to update firmware. Will always update EEPROM if firmware update by FTDI or MIDI is selected from drop-down menu.

Important: Please update firmware twice, otherwise Button Remaps may contain 
garbage. With update by FTDI or MIDI using HX3.5 Editor, updating firmware 
is sufficient. "Finalize" with HX3.5 Editor or by SD card INI script after update.

<b>08/16/2018</b> Firmware #5.090, Scan Driver #14, HX3.5 Editor 

* Bugfix: GM Voice save to Overall Preset
* Bugfix: External Rotary control switch (Extension Board) 
* Bugfix: "randomly very low velocity sent" in Scan Driver 
* GM voices minor bugfix 
* HX3.5 Editor allows mapping of "extra" upper/lower/pedal voices #16..23 to any GM program number (see new 
"DSP/GM Setup" group). Click "Save Params as Default" after editing to activate new mapping.
* Lowered "Relative Organ Volume" param 1491 (see DSP/GM Setup Group in HX3.5 Editor) to 64 for better match to GM voices

Note: Disable Param 1497 (Sync Voice Numbers) in "System Inits" to enable GM 
Voice numbers saved in Overall Presets. From this FW and up, param 1497 will be disabled 
by default. **Do "Finalize" with HX3.5 Editor after update!**

<b>08/13/2018</b> Firmware #5.087, Scan Driver #12, DSP #01.02

* Mixture Drawbars will no longer sound on B3 and Combo Organ Models
* Phasing Rotor modulation enhanced 
* Sostenuto pedal changed from MIDI CC $42 to $45 (69 dec.) due to NI B4 Perc CC conflict. Without this update, HX3 Drawbar 
controller PERC ON will not work.
* DSP #01.02 will send CC $45 on Sostenuto pedal changes now
* MAG Organs only: Amp 122 volume will have a minimal amount

<b>07/30/2018</b> Firmware 5#.085, HX3.5 Editor

* Firmware, Scan Driver and FPGA update via MIDI, MIDI over USB or FTDI cable possible (needs one-time update via SD card)
* HX3.5 Editor version 5.08 also works with MIDI or MIDI over USB connection (no driver required on Windows PCs)
* Bugfix on Drawbar Mixture setup
* Bugfix Overall Preset Handling

<b>07/07/2018</b> Firmware #5.082, SD Card INI Scripts

* INI Script ReadLn bug fixed
* INI Scripts were corrupted (LF instead of CRLF)

<b>07/02/2018</b> Firmware #5.080, FPGA #09072018

* "Common Preset Save" Bug fixed
* Lower default leakage, was way too high 
* Issue with ENV_ENA Bits fixed, electronic gating was permanently on
* Various minor bugs fixed

Dateiliste
==========

Dokumente
---------

Schaltpl�ne und Audio-Routing-Blockdiagramme

Hilfsprogramme
--------------

"HX35_Editor_506": Editor/Parameter-Einstellung f�r HX3.5-Modul 
und HX3.5-Mainboard ab *Firmware 5.06* mit neuer Parameter-Struktur �ber 
serielle Schnittstelle mit FTDI-Kabel. Ben�tigt die im gleichen Ordner 
enthaltenen Dateien. F�hrt auch Updates und Finalisierung aus (Balfer). F�r 
Firmware ab 5.06 unbedingt HX35_Editor_506 benutzen! 

"HX35_Tapering": Editor f�r Lautst�rketabellen Hammond-Tapering (0 bis 3, B3 155 
bis B3 Recapped). Gegen�ber 3.4 angepasste Dateinamen und Speicherung der 
Einstellungen in INI-Datei.

"HX35_MIDIremote": Testprogramm f�r SEMPRA-MIDI-CC-Set mit allen �ber MIDI 
fernsteuerbaren Drawbars und Tabs. Testfunktion f�r SysEx-Daten. Nach dem Start 
angeschlossenes MIDI-Interface ausw�hlen. Ben�tigt ein USB-MIDI-Adapterkabel 
oder dgl. am PC.

"WavesetDesigner": Q&D-Editor f�r Wavesets. Nicht perfekt. Kann Generator-
Wavesets per Fouriersynthese erstellen, einfach per Schieberegler Oberton-
Anteile bestimmen.

Update-Dateien
--------------

Die f�r das Update n�tigen Dateien sind in den Ordnern HX35_SDCARD_XXX 
(XXX=OEM/Hersteller) enthalten. Achtung: Modul und Mainboard verwenden 
unterschiedliche FPGA-Konfigurationen!

Die Skripte werden vom AVR auf dem HX3.5-Modul direkt von SD-Karte abgespielt. 
Sie k�nnen Befehle zum Update des Flash-Speichers enthalten (Firmware, FPGA-
Konfiguration, ScanCores, Taperings, Generator-Wellenformen), aber auch 
nachtr�glich Parameter nach Wunsch �ndern. Die Skripte k�nnen �ber das HX3-
MenuPanel aufgerufen werden (nicht bei OEM-Modul-Firmware).

"autorun.ini": Skript zum automatischen Update. Kann auch Finalisierung 
durchf�hren (Lizenzen setzen). Ein Skript mit diesem Namen wird automatisch beim 
Booten ausgef�hrt und nach erfolgreichem Durchlauf in "_autorun.ini" umbenannt.

"update.ini": Skript zum Komplett-Update einschlie�lich FPGA und Firmware, wie "autorun.ini"

"waveupd.ini": Skript zum Update nur der Generator-Wellenformen

"coreupd.ini": Skript zum Update nur der ScanCore(s) und der Taperings

"taperupd.ini": Skript zum Update nur der Taperings

"scanupd.ini": Skript zum Update nur des Scan-Drivers (scan.dat), kann f�r MIDI oder Fatar sein

"scanmidi.ini": Skript zum Update nur des Scan-Drivers auf MIDI IN (hx_midi.dat)

"scanfatr.ini": Skript zum Update nur des Scan-Drivers auf FatarScan2 (hx_fatar.dat)


F�r ein Komplett-Update sind folgende Dateien n�tig:

"scan.dat": ScanCore (kann f�r MIDI oder Fatar sein), 

"taper1.dat"..."taper4.dat": Generator-Ausgangspegel und Manual Taperings (4 Sets), 

"waveset0.bin"..."waveset7.bin": Generator-Wellenformen (8 Sets mit je 8 Wellenformen),

"fir_coe.dat": FIR-Filterkoeffizienten f�r Leslie-Horn,

"firmware.bin": Firmware-Image f�r AVR, Flash-Inhalt,

"eeprom.bin": Firmware-Image f�r AVR, EEPROM-Inhalt
