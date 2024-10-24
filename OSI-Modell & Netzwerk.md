Protokoll (Regel)
WLAN funktioniert durch elektromagnetische Wellen, sie stören sich nicht, weil sie unterschiedliche Frequenzen haben

| Layer | Adressen | Protokolle |
| ----- | -------- | ---------- |
| L1    |          |            |
| L2    | MAC      | Ethernet   |
| L3    | IP       |            |
| L4    | Port     |            |
|       |          |            |

Ein Router verbindet 2 oder mehr IP-Netzwerke.

IP Netzmaske
255.255.255.0
in Binär: 11111111.11111111.11111111.00000000

Wenn die ersten 24 Binärzahlen gleich sind dann gehören sie zum selben Netzwerk. (Deswege /24)
1.1.1.1/24
00000001.00000001.00000001.00000001
Also bis hier hin                          |
1.1.1.0/24
00000001.00000001.00000001.00000000

Adress Resolution Protocol
ARP liegt zwischen L2 und L3
