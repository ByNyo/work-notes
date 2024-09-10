## Was ist eine Datenbank?
Eine Datenbank ist eine elektronisch gespeicherte, systematische Sammlung von Daten, die jede Art von Daten enthalten kann. Zum Beispiel Wörter, Zahlen, Bilder, Videos und Dateien. Um gespeicherte Daten zu speichern, abrufen oder bearbeiten kann man eine Software nutzen, diese wird Datenbankmanagementsystem oder kurz DBMS genannt.
## Arten von Datenbanken
### Hierarchische Datenbank
Diese Art war in den 1970ern sehr populär. Anstatt Datensätze sequentiell zu speichern, wurden Hierarchische Datenbanken als Baumstruktur dargestellt, dadurch wurde eine über- und untergeordnete Beziehung zwischen zwei Dateien hergestellt.
Zum Beispiel um ein Datenbanksystem für ein Möbeleinzelhandelsgeschäft zu erstellen, kann man *Schlafzimmer* als übergeordneten Datensatz mit *Bett, Nachttisch* und *Kleiderschrank* als untergeordnete Datensätze definieren. Diese könnten auch weitere untergeordnete Elemente, wie beim *Bett-Datensatz* ein *Einzelbett, Doppelbett, usw. enthalten*. Das Implementieren dieses Datenmodells war leider sehr komplex und konnte ohne signifikante Datenduplikation nicht mit mehreren über- und untergeordneten Beziehungen umgehen.
### Netzwerkdatenbank
Das Netzwerkdatenmodell hat es ermöglicht einem untergeordneten Datensatz, mehrere andere Datensätze überzuordnen und andersrum auch. Wenn man zum Beispiel in einem Möbelhaus zwei übergeordnete Datensätze hat, *Schlafzimmer* und *Kinderzimmer*, könnnen beide mit dem untergeordneten Datensatz Garderobe verknüpft werden.
### Relationale Datenbank
DIe relationale Datenbank entwickelte sich in den 1980er Jahren aufgrund ihrer Produktivität, Flexibilität und Kompatibilität mit schnellerer hardware zu einem beliebten Unternehmensmodell. Relationale Datenbanken organisierten Datenstze als mehrere Tabellen anstelle von verknüpften Listen.
In einem relationalen Datenbankmodell hat jede Kategorie eine Tabelle mit Kategorieattributen als Spalten und Datensätze als Zeilen. Zum Beispiel können sie das Möbelgeschäft als eine Reihe von Tabellen modellieren - *Räume* und *Möbel*. Die Tabellen sind durch die Spalten *Raumnummer* und *Möbelname* verknüpft. Beide Spalten werden auch ***Primärschlüssel*** genannt.
### Objektorientierte Datenbank
Objektorientierte Datenbanken entwickelten sich in den 1990er Jahren als Reaktion auf das Aufkommen der objektorientierten Programmierung. Programmierer und Designer begannnen, die Daten in ihren Datenbanken als Objekte zu behandeln. Beispielsweise kann man die Attribute eines Stuhls, wie Farbe und Größe, einem *Stuhl-Datenobjekt* zuordnen. Dieses Objekt ist eine virtuelle Darstellung des realen Stuhls in der objektorientierten Datenbank.
### NoSQL-Datenbank
SQL ist eine Abfragesprach, mit der man Daten in relationalen Datenbanken abrufen, zugreifen und bearbeiten kann. NoSQL ist genau das Gegenteil dazu, es ist ein Datenbankmechanismus der bei der Datenmodellierung keine tabellarischen Beziehungen verwendet.
NoSQL-Datenbanken wurden zu Beginn der 2000er Jahre erstellt, als Cluster-Datenverarbeitung und verteilte Datenbankarchitekturen entstanden sind. Verteilte Architekturen speichern eine große Datenbank übermehrere zugrunde liegende Speichergeräte. Diese Anordnung wird als horizontale Skalierung bezeichnet.
Softwaremechanismen in NoSQL sind hohe Geschwindigkeit, keine Notwendigkeit für feste Tabellenschemata, die Fähigkeit, doppelte oder gruppierte Daten zu speichern und die Fähigkeit, horizontal zu skalieren.
### Cloud-Datenbank
Cloud-Datenbanken laufen auf ein Cloud-Datenverarbeitungsplattformen. Mittlerweile gibt es zwei Standardbereitstellungsmodelle: Benutzer können Datenbanken unabhängig in der Cloud ausführen oder Zugriff von einem Cloud-Datenbankanbieter erwerben. Cloud-Datenbanken können sowohl SQL- als auch NoSQL-Datenmodelle nutzen. 
### Graphdatenbank
Graphdatenbanken sind nützlich, da sie die Beziehungen zwischen verschiedenen Datensätzen priorisieren. Sie sind speziell zum Speichern und Navigieren von Beziehungen konzipiert. Eine Graphdatenbank besteht aus *Knoten* und *Edges*. Knoten speichern Datenobjekte und Edges speichern Beziehungen zwischen Objekten. Ein Edge hat immer einen Startknoten, einen Endknoten, einen Typ und eine Richtung. Er kann Beziehungen zwischen über- und untergeordneten Elementen, Handlungen und Eigentüümerschaften beschreiben. Die Anzahl und Art der Beziehungen in einem Knoten ist nicht beschränkt.
### In-Memory-Datenbank
Eine In-Memory-Datenbank befindet sich, ganz im gegensatz zu den meisten Datenbanken nicht auf externen Speichergeräten, sondern im internen Speicher eines Computers. Sie wird jedoch in der Regel auch durch Computerdatenspeicher gesichert. In-Memory-Datenbanken sind schneller als Festplattendatenbanken. Sie werden häufig dort eingesetzt, wo die Reaktionszeit von entscheidender Bedeutung ist, z. B. in Telekommunikationsnetzwerken.

## Wofür werden Datenbanken verwendet?
### Betrugserkennung
Graphdatenbanken helfen beim Identitätsmanagement und bei der Betrugserkennung. Algorithmen für Machine Learning finden Muster und erkennen betrügerische Aktivitäten automatisch und präventiv.
### Dokumentenverwaltung
NoSql-Datenbanken speichern und verwalten Dokumente, wie Artikel und Verträge. Sie ermöglichen es Unternehmen auch, Dokumente abzufragen und zu indizieren.
### Spiele und Unterhaltung
Viele Spiel- und Unterhaltungsunternehmen nutzen Datenbanken in großem Umfang, um reichhaltige Medienerlebnisse zu bieten, z. B. den gleichzeitigen Anmeldezuigriff für Millionen von Benutzern.