# HX3.5

![GitHub Logo](https://github.com/keyboardpartner/HX35/blob/master/HX35_k.JPG)

***

## Firmware and Docs for HX3 mk5

**WICHTIG: Bitte entpacken Sie die ZIP-Files in einen Ordner auf Ihrer lokalen 
Festplatte. Starten Sie HX3 Editor aus diesem Ordner. Beim Start direkt im ZIP-
Fenster schl�gt das Update fehl.**

Zum Update Files im Ihr Ger�t betreffenden ZIP-File "SDCARD" auf eine (leere) SD- oder 
SDHC-Karte kopieren, in den SD-Kartenadapter einsetzen und HX3.5 mit 
Stromversorgung verbinden (Neustart).

**IMPORTANT: Be sure to extract all files to a local hard disk folder. Update 
will fail if started directly from ZIP window.**

To update HX3.5, unzip and copy all files from appropriate ZIP file "SDCARD" to empty SD 
or SDHC card. Insert SD card in HX3.5 card adaptor and power up HX3.5 (Reset/Restart).  

### Changelog

<b>07/30/2018</b> Firmware 5.085, HX3.5 Editor

* Firmware, Scan Driver and FPGA update via MIDI, MIDI over USB or FTDI cable possible (needs one-time update via SD card)
* HX3.5 Editor version 5.08 also works with MIDI or MIDI over USB connection (no driver required on Windows PCs)
* Bugfix on Drawbar Mixture setup
* Bugfix Overall Preset Handling

<b>07/07/2018</b> Firmware 5.082, SD Card INI Scripts

* INI Script ReadLn bug fixed
* INI Scripts were corrupted (LF instead of CRLF)

<b>07/02/2018</b> Firmware 5.080, FPGA #09072018

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
