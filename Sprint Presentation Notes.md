
# Notes
### Prozess
- **Was ist es?**
	- konkrete Instanzierung eines Programms zur Ausführung innerhalb des Rechnersystems
- **Sicher?**
	- abgeschottet von anderen Programmen
	- jeder hat eigenen Memory-Platz (können einander nicht stören)
- **Bestandsteile** (besteht aus)
	- Processor registers
	- Program counters (Thread)
	- Stack pointers (Thread)
	- Memory pages (Thread)
	- besteht aus einem Main-Thread 
	- meistens noch weitere Threads

### Thread
- **Bestandsteile** (besteht aus)
	- Stack (Umfang der Memory)
	- Registers (Teile des Speicherplatzes auf der CPU)
	- Program counters (Spezielles Register behält Speicheradresse (Memory) im Auge)
- (Nächste Folie) **Was ist es**?
	- Ausführungsreihenfolge in Abarbeitung eines Programms
- **Was macht er?**
	- teilt sich Memory mit anderen Threads
	- Falls ein Thread sich falsch Verhält (kann Prozess-Absturz passieren)
### Goroutine
- **Funktion**
	- Fundament von Concurrency (Parallelität / Gleichzeitigkeit)
	- ein leichtgewichter Ausführungsprozess (leichter Thread)
- **Ausführung**
	- läuft gleichzeitig mit anderen goroutines
	- im Gegensatz zu normalen Threads (gemanaged von Go runtime)
	- durch Go runtime mehr effizient in CPU-Auslastung und Memory
- **Schreibweise** (siehe Board)
### CPU
- **Was ist es?**
	- Central Processing Unit
	- Herz eines Computers
- **Was macht es?** 
	- verarbeitet Signale bzw. Anweisungen
		- Recheneinheit verarbeitet entgegengenommene Befehle
		- Recheneinheit gibt entsprechende Ergebnisse zurück
	- berechnet Prozesse und Threads
	- Datenaustausch
- **Technische Daten**
	- Architektur (Beispiele)
		- x86
		- x64
		- ARM
		- usw.
	- Taktfrequenz
		- Basis-Takt (meist in GHz)
		- Turbo-Boost-Takt (spezielle Modelle)
	- Cache
		- L1-Cache (pro Kern)
		- L2-Cache (pro Kern)
		- L3-Cache (pro Kern)
	- Unterstützte Speicher
		- Arten von RAM
			- DDR4
			- DDR5
		- Maximale RAM-Kapazität
	- Stromverbrauch
		- TDP (Thermal Design Power) in Watt
	- Sockeltype
		- der benötigte Sockel für Mainboard (z.B. LGA, PGA, BGA)
	- Kerne
		- physiche Kerne
		- logische Kerne (Hyper-threading)
### Hyper-threading
- Warum? - Intel (Entwickler)
	- bessere Nutzung der CPU-Ressourcen
	- Verbesserung der Multitasking-Fähigkeiten
- Virtuelle Kerne
	- erstellt zwei virtuelle Kerne (oder logische Prozessoren) aus einem physichen Kern
	- ein physicher Kern kann 2 Threads gleichzeitig ausführen
- Vorteile
	- Leistungssteigerung
	- verbesserte Effizienz
- Nachteile
	- nicht doppelte Leistung
		- die Rechenleistung eines Kerns nicht verdoppelt
		- Leistung abhängend von vielen Faktoren
		- nicht alle Anwendungen profitieren gleichmäßig
	- Komplexität in der Software
		- Software muss Hyper-Threading unterstützen
		- Leistungsverlust ohne Optimierung
- Fazit
	- effektive Technologie zur Optimierung der Nutzung der Ressourcen eines Prozessors
	- viele Anwendungen sind stark auf parallele Verarbeitung angewiesen
### ASCII
- American Standard Code for Information Interchange
- repräsentiert Text in Computern, Telekommunikationsequipment und anderen Geräten
### Unicode
- Internationaler Verschlüsselungsstandard
- genutzt von unterschiedlichen Skripten und Sprachen
- einzigartigen Zahlenwert (unique numeric value)
### UTF
- Unicode Transform Format
- Charakter in einem standartisierten Weg zu verschlüsseln und entschlüsseln
- **3 unterschiedliche Formate**
	- UTF-8 (sequence of one to four 8-bit bytes)
	- UTF-16 (sequence of one or two 16-bit code units)
	- UTF-32 (a single 32-bit code unit)
- **jeder UTF-8**
	- weniger Internationalisierungsprobleme als andere Charakter-Verschlüsselungen
### Makefiles
- **Wofür wird es genutzt?**
	- kompilieren
	- andere Sachen (wie bash)
- **Wie wird es genutzt?**
	- Ziele (Targets)
	- Commands in Targets
	- Ausführung der commands in Reihenfolge
- **.PHONY**
	- damit Make das Target nicht als Dateiname nimmt sondern als Target
### Environment Variables
- erstellen oder verändern einer Umgebungsvariable
- zeigen von environment variables
- $PATH
	- speichert Wege zu commands und scripts
	- Befehle in $PATH Ausführung überall im Terminal
	- Beispiel
### SSD vs HDD
- **Solid State Drive**
- Vorteile
	- schneller
		- Beispiel (schnellster SSD)
		- Lesegeschwindigkeit (bis zu 14.500 MB/s)
		- Schreibgeschwindigkeit (bis zu 12.700 MB/s)
	- leiser
	- kühler
	- sehr zuverlässig (weil elektrisch)
- Nachteile
	- teurer
	- keine Datenwiederherstellung (weil elektrisch)
- **Hard Disk Drive**
- Vorteile
	- günstiger (weil langsamer)
	- größere Speichervolumen (beliebt bei Firmen, weil günstig)
	- einfache Datenwiederherstellung (wegen speichern auf Metalplatte)
- Nachteile
	- langsamer, lauter & wärmer (wegen mechanischer Teile)
### Fazit HDD vs SSD
- SSD
	- Gamer (wegen schneller Performance)
- HDD
	- speichern große Datenmengen
	- nur bestimmtes Budget
## For Image
### Create / Change / Remove
```bash
export <environment>=<value> # To create or change an environment variable
```
### How to get environment variables
```bash
env # Prints all Environment Variables

printEnv <environment> # Prints a specified environment variable

echo $<environment> # Prints a specified environment variable
```
##### What is $PATH?
- stores all commands and scripts
- checks for commands and scripts
- executes command / script or throws error
`/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin`




