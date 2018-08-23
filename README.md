# HX3.5

![HX35 Board](https://github.com/keyboardpartner/HX35/blob/master/HX35_k.JPG)

## Firmware and Docs for HX3 mk5

**IMPORTANT: Be sure to extract all ZIP files to a local hard disk folder. Update 
will fail if started directly from ZIP window.**

Updates for HX3.5 consist of several parts:

* Firmware (firmware.bin and eeprom.bin), handles user interface and MIDI CC
* FPGA Sound Engine (hx3_main.bin), sound generation
* Scan Driver (scanXXX.dat), handles keyboard scanning or MIDI receive
* Wavesets (wavesetX.bin), waveform definitions for Sound Engine, different organ models
* Taperings (taperX.dat), B3/H100 tone generator filters and manual tapering definitions
* FIR coefficients (fir_coe.dat), coefficient file for rotary horn simulation

Files may be used independently and may carry different time stamps.

Please download the ZIP file dedicated for your particular product 
configuration. Unzip and copy all files from appropriate ZIP file "UPDATE" to a 
local folder on your harddisk. 

Updates are possible by one of the following methods:

* via [HX3.5 Editor with MIDI connection](http://wiki.keyboardpartner.de/index.php?title=HX3.5_Update_by_MIDI) (Windows operating system required, all devices)
* via [HX3.5 Editor with FTDI USB/serial adaptor cable connection](http://wiki.keyboardpartner.de/index.php?title=HX3.5_Update_by_FTDI_or_Extension_Board_mk4) (Windows operating system and access to board connectors required)
* via [HX3.5 Editor with old Extension Board mk4](http://wiki.keyboardpartner.de/index.php?title=HX3.5_Update_by_FTDI_or_Extension_Board_mk4#Extension_Board_mk4_connection) (Windows operating system required)
* via [SD Card and SD Card slot adaptor](http://wiki.keyboardpartner.de/index.php?title=HX3.5_SD_Card_Usage), available separately (access to board connectors required)
 

### Changelog

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

Schaltpläne und Audio-Routing-Blockdiagramme

Hilfsprogramme
--------------

"HX35_Editor_506": Editor/Parameter-Einstellung für HX3.5-Modul 
und HX3.5-Mainboard ab *Firmware 5.06* mit neuer Parameter-Struktur über 
serielle Schnittstelle mit FTDI-Kabel. Benötigt die im gleichen Ordner 
enthaltenen Dateien. Führt auch Updates und Finalisierung aus (Balfer). FÜr 
Firmware ab 5.06 unbedingt HX35_Editor_506 benutzen! 

"HX35_Tapering": Editor für Lautstärketabellen Hammond-Tapering (0 bis 3, B3 155 
bis B3 Recapped). Gegenüber 3.4 angepasste Dateinamen und Speicherung der 
Einstellungen in INI-Datei.

"HX35_MIDIremote": Testprogramm für SEMPRA-MIDI-CC-Set mit allen über MIDI 
fernsteuerbaren Drawbars und Tabs. Testfunktion für SysEx-Daten. Nach dem Start 
angeschlossenes MIDI-Interface auswählen. Benötigt ein USB-MIDI-Adapterkabel 
oder dgl. am PC.

"WavesetDesigner": Q&D-Editor für Wavesets. Nicht perfekt. Kann Generator-
Wavesets per Fouriersynthese erstellen, einfach per Schieberegler Oberton-
Anteile bestimmen.

Update-Dateien
--------------

Die für das Update nötigen Dateien sind in den Ordnern HX35_SDCARD_XXX 
(XXX=OEM/Hersteller) enthalten. Achtung: Modul und Mainboard verwenden 
unterschiedliche FPGA-Konfigurationen!

Die Skripte werden vom AVR auf dem HX3.5-Modul direkt von SD-Karte abgespielt. 
Sie können Befehle zum Update des Flash-Speichers enthalten (Firmware, FPGA-
Konfiguration, ScanCores, Taperings, Generator-Wellenformen), aber auch 
nachträglich Parameter nach Wunsch ändern. Die Skripte können über das HX3-
MenuPanel aufgerufen werden (nicht bei OEM-Modul-Firmware).

"autorun.ini": Skript zum automatischen Update. Kann auch Finalisierung 
durchführen (Lizenzen setzen). Ein Skript mit diesem Namen wird automatisch beim 
Booten ausgeführt und nach erfolgreichem Durchlauf in "_autorun.ini" umbenannt.

"update.ini": Skript zum Komplett-Update einschließlich FPGA und Firmware, wie "autorun.ini"

"waveupd.ini": Skript zum Update nur der Generator-Wellenformen

"coreupd.ini": Skript zum Update nur der ScanCore(s) und der Taperings

"taperupd.ini": Skript zum Update nur der Taperings

"scanupd.ini": Skript zum Update nur des Scan-Drivers (scan.dat), kann für MIDI oder Fatar sein

"scanmidi.ini": Skript zum Update nur des Scan-Drivers auf MIDI IN (hx_midi.dat)

"scanfatr.ini": Skript zum Update nur des Scan-Drivers auf FatarScan2 (hx_fatar.dat)


Für ein Komplett-Update sind folgende Dateien nötig:

"scan.dat": ScanCore (kann für MIDI oder Fatar sein), 

"taper1.dat"..."taper4.dat": Generator-Ausgangspegel und Manual Taperings (4 Sets), 

"waveset0.bin"..."waveset7.bin": Generator-Wellenformen (8 Sets mit je 8 Wellenformen),

"fir_coe.dat": FIR-Filterkoeffizienten für Leslie-Horn,

"firmware.bin": Firmware-Image für AVR, Flash-Inhalt,

"eeprom.bin": Firmware-Image für AVR, EEPROM-Inhalt
