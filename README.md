# HX3.5
Firmware and Docs for HX3 mk5


Dateiliste f�r Updates
======================

Dokumente
---------

"Controllerliste HX35_custom.xls": Excel-Tabelle mit HX3.5-MIDI-CCs und CSV-Export 
f�r "hx35_organ.csv". 

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

"waveset0.bin"..."waveset7.bin": Generator-Wellenformen (8 Sets),

"fir_coe.dat": FIR-Filterkoeffizienten f�r Leslie-Horn,

"firmware.bin": Firmware-Image f�r AVR, Flash-Inhalt,

"eeprom.bin": Firmware-Image f�r AVR, EEPROM-Inhalt


================================
-cm 1.2.2018