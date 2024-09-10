### **CPU**
A CPU (Central Processing Unit) is the primary component of any computer or electronic device. It acts as the "brain" of the computer, by reading and interpreting commands from software programs and use them to control other components within the machine.

The CPU speed is measured in hertz (Hz). Processors with higher hertz values will be able to process insturctions faster.
##### Definiton
The Central Processing Unit (CPU) forms the heart of any computer system, controlling the flow of data and instructions to carry out a range of tasks. It is an essential component in any modern computing system.

### **Hyperthreading**
One Physical core works like two "logical cores" that can handle different software threads. Two logical cores can work through tasks more fficiently than a tradiotional signle-threaded core.
![[Multithreading.png]]
##### Benefits
The PC can process more information in less time and run more background tasks without disruption.
### **SSD vs HDD (performance implications)**
#### Solid State Drive (SSD)
**Funktionsweise:** SSDs speichern Daten auf elektrischen Schaltungen
**Prozess lesen:** SSD-Controller findet richtige Adresse und liest ihre Ladungen
**Prozess schreiben:** SSD kopiert Daten in einen neuen Block und löscht dann den alten Block. Anschließend schreibt es neu in den alten Block, indem es seine Ladungen ändert.
**Leistung:** SSDs sind schneller, leise und laufen kühler.
**Kosten:** SSDs sind teurer.
**Zuverlässligkeit:** SSDs sind elektrisch, wodurch sie weniger anfällig für Beschädigungen sind.
#### Hard Disk Drive (HDD)
**Wie löschen sie Daten?**
- schreibt eine Reihe von Nullen, Einsen oder bedeutungslose Pseudozufallsdaten auf die Sektoren
**Wie überschreiben sie Daten?**
- ersetzt Daten die vorher dort wahren mit neuen Daten (schreibt neue Daten über alte Daten)
**Funktionsweise:** HDDs speichern Daten auf mechanisch beweglichen, magnetischen Platten.
**Prozess lesen:** HDD-I/O-Controller sendet ein Signal, das den Aktuatorarm bewegt. Der Schreib-/Lesekopf liest dann Ladungen.
**Prozess schreiben:** Eine HDD bewegt den Schreib-/Lesekopf an den nächstgelegenen verfügbaren Ort. Anschließend schreibt es Daten indem es die Ladung der Bits in diesem Bereicht ändert.
**Leistung:** HDDs sind langsamer, da sich ihre Platten bewegen müssen. Sie geben mehr Wärme ab und sind lauter.
**Kosten:** HDDs sind kostengünstiger und größere Speichervolumen sind komerziell beliebt.
**Zuverlässligkeit:** HDDs haben bewegliche mechanische Teile, die sie vergleichsweise weniger langlebig machen
### **Memory swapping**
Memory swapping creates a larger virtual space (for RAM) by combining the physical memory and hard disk space. Unused memory contents are **swapped** to the disk, which can be restored later. As a result, the physical memory becomes free and can run other operations.

### **Task**
Cache Layers: 4 (including 0)
Sizes:
- L0 Cache: 192 KiB
- L1 Cache: 128KiB
- L2 Cache: 2MiB
- L3 Cache: 8Mib

![[lstopo.png]]
