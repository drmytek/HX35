![GitHub Logo](https://github.com/keyboardpartner/HX35/blob/master/HX35_k.JPG)


***

# HX3.5

## Firmware and Docs for HX3 mk5

## HX3 Latest Firmware

#### Final releases for update with HX3 Remote application

**WICHTIG: Bitte entpacken Sie die ZIP-Files in einen Ordner auf Ihrer lokalen Festplatte. Starten Sie HX3 Editor aus diesem Ordner. Beim Start direkt im ZIP-Fenster schlägt das Update fehl.**

**IMPORTANT: Be sure to extract all files to a local hard disk folder. Update will fail if started directly from ZIP window.**

New: Complete update packages for most common HX3 instruments for a hassle-free update to newest version. 
The ZIPs Flash_XXX.zip contain only the files needed for your instrument. 
You don't need the other HX3 stuff offered here, just make sure you use **only the new files and HX3 Flash utility** contained in dedicated ZIP package. 


Dateiliste für Updates
======================

Dokumente
---------

"Controllerliste HX35_custom.xls": Excel-Tabelle mit HX3.5-MIDI-CCs und CSV-Export 
für "hx35_organ.csv". 

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

"waveset0.bin"..."waveset7.bin": Generator-Wellenformen (8 Sets),

"fir_coe.dat": FIR-Filterkoeffizienten für Leslie-Horn,

"firmware.bin": Firmware-Image für AVR, Flash-Inhalt,

"eeprom.bin": Firmware-Image für AVR, EEPROM-Inhalt


================================
-cm 1.2.2018