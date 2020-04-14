# Montagsupdates
_Im Rahmen der Projektförderung durch den [Prototype Fund](https://prototypefund.de) berichten wir wöchentlich über unseren Fortschritt, neueste Updates zuerst._

## Woche 6 (Update zum ~~13.~~ 14. April)
### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1) (ab jetzt hauptsächlich nur noch der "betreiben"-Anteil)
 2. [Statistische Analyse der gesammelten Echtzeit-Verspätungs-Daten](https://github.com/dystonse/dystonse/milestone/2)
 3. [Prognose-Berechnung entwickeln](https://github.com/dystonse/dystonse/milestone/3)

### Das haben wir letzte Woche gemacht
(wie immer: viel Text, aber diesmal auch ein paar Bilder!)

 * Einfache, quantitative Visualisierungen der bisher gesammelten Daten, um die Menge und Qualität der Daten einzuschätzen (schwankt leider sehr).
 * Versuch, die verschiedenen Varianten von (Bus-)Linien zu verstehen und algorithmisch zu verstehen. Dabei entstehen unhandliche Grafiken wie die folgende: [haltestellen_03.png](img/haltestellen_03.png).
 * Visualisierung von einzelnen (Sub)Routen in Raum-Zeit-Diagrammen im Stil von [Bildfahrplänen](https://de.wikipedia.org/wiki/Bildfahrplan) als neue Funktion unseres [dystonse-gtfs-data](https://github.com/dystonse/dystonse-gtfs-data)-Tools implementiert. Beispiel siehe unten.
 * Die Datenstrukturen für `Trip`s im Paket [gtfs-structures](https://github.com/rust-transit/gtfs-structure) um ein Feld für die optionale `shape_id` aus dem GTFS-Standard erweitert, die wir auch für unsere Visualisierung nutzen, und dafür einen Pull request erstellt.
 * In unserer Version der [gtfs-structures](https://github.com/dystonse/gtfs-structure) ein neues Feld `route_variant` eingeführt, dessen Wert aus der Haltestellen-Abfolge berechnet wird (damit weichen wir zwar vom GTFS-Standard ab, aber es ist zuverlässiger, da die optionale `shape_id` von einem der Anbieter, die wir aktuell verwenden, oft nicht angegeben wird.)
 * Ein neues [Repository für manuelle Tests](https://github.com/dystonse/dystonse-tests) angelegt, um für "mal eben schnell gucken, ob die Daten jetzt richtig aussehen" weniger in unserem eigentlichen Code rumbasteln zu müssen.

### Bilder
Die Menge der Daten, die wir über die Tage verteilt sammeln konnten:

![Datenmenge](img/Datenmenge_02.png)

Hier ein Beispiel für einen von uns generierten Bildfahrplan:

![Bildfahrplan](img/Bildfahrplan_01.png)

Auf der Y-Achse schreitet von unten nach oben die Zeit voran, hier also von etwa 12:00 bis 18:00. Von links nach rechts verläuft die Buslinie 430 in Oldenburg. Die Bedeutung der Linien je nach Farbe:

 * **schwarz:** Der Verlauf laut Fahrplan
 * **grün:** Reale Fahrten an einem Wochentag
 * **rot:** Reale Fahrten an einem Sonntag

### Das machen wir diese Woche
 * Datenqualität sichten und prüfen, ob wir systematische Fehler beim Sammeln / Import gemacht haben
 * ggf. Fehler beheben und neu importieren
 * weitere Analyse der Echtzeitdaten, auf dass wir bald zu einem statistischen Modell für die Prognose kommen
 * ggf. neuer Blog-Post zu unseren Erkenntnissen und Zwischenergebnissen
 
### Das bremst uns gerade
 * Andere Jobs und private Aufgaben
 * die ungewisse Zukunft (Absage vieler Veranstaltungen etc. durch die Corona-Krise) drückt mittlerweile schon etwas auf unsere Stimmung und Energie

### Das motiviert uns gerade
 * Mit der Visualisierung der Daten haben wir direkt etwas sichtbares als Ergebnis.

## Woche 5 (Update zum 6. April)
### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1) (ab jetzt hauptsächlich nur noch der "betreiben"-Anteil)
 2. [Statistische Analyse der gesammelten Echtzeit-Verspätungs-Daten](https://github.com/dystonse/dystonse/milestone/2)
 3. [Prognose-Berechnung entwickeln](https://github.com/dystonse/dystonse/milestone/3)

### Das haben wir letzte Woche gemacht
 * Fehlerbehandlung und Ausgabe von Erfolgsstatistiken im [Importer](https://github.com/dystonse/dystonse-gtfs-importer) verbessert.
 * Datensammlung und -import für eine weitere Datenquelle eingerichtet, so dass wir nun Daten von [VBN](https://www.vbn.de/) und [VRN](https://www.vrn.de/) gleichzeitig aufzeichnen.
 * Früher gesammelte Daten (von unserem ersten Testserver) zusätzlich in die aktuell genutzte Datenbank importiert.

### Das machen wir diese Woche
 * Erste statistische Analysen der bisher gesammelten Daten, um ein Gefühl dafür zu bekommen, mit welchen Einflussfaktoren wir beim Prognose-Modul anfangen.
 * Mit der Entwicklung der Software-Komponente für die Prognoseberechnung beginnen.
 
### Das bremst uns gerade
 * Nachdem wir im vorigen Monat recht viel Zeit in dieses Projekt gesteckt hatten, haben wir uns letzte Woche etwas mehr Zeit für Erholung genommen und uns mehr um private Angelegenheiten gekümmert.

### Das motiviert uns gerade
 * Programmieren in Rust macht Spaß
 * Wir haben unsere erste wichtige Komponente im Wesentlichen fertig und können jetzt bald mit ganz neuen Teilen anfangen


## Woche 4 (Update zum 30. März)
### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1)
 2. [Statistische Analyse der gesammelten Echtzeit-Verspätungs-Daten](https://github.com/dystonse/dystonse/milestone/2)

### Das haben wir letzte Woche gemacht
 * Datensammlungs-Skripte und Importer in [Docker-Setup](https://github.com/dystonse/dystonse-docker) integriert
 * [Importer](https://github.com/dystonse/dystonse-gtfs-importer) so erweitert, dass mehrere Dateien auf einmal verarbeitet werden können.
 * Anschließend automatischen Modus hinzugefügt, mit dem kontinuierlich neue Daten erkannt und in die Datenbank importiert werden.

### Das machen wir diese Woche
 * Datensammlung robuster machen (Fehlerbehandlung, Monitoring, etc.)
 * Analyse der bisher gesammelten Daten (zunächst Datenqualität und -Menge, dann Statistik über Verspätungen)
 * Anlegen von neuen Datenquellen automatisieren 
 * evtl. mit der Entwicklung der Software-Komponente für die Prognoseberechnung beginnen
 
### Das bremst uns gerade
 * Durch das Corona-Virus ist Nahverkehr gerade kein besonders populäres Thema, was z.B. Nutzer\*innen-Befragungen schwierig machen könnte
 * andere Jobs und Verpflichtungen

### Das motiviert uns gerade
 * Dass wir zwei gemeinsam im selben Homeoffice arbeiten können (das sogenannte "Social Dystonsing" 😉)

## Woche 3 (Update zum 23. März)
### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1)
 2. [Statistische Analyse der gesammelten Echtzeit-Verspätungs-Daten](https://github.com/dystonse/dystonse/milestone/2)
 3. [Prognose-Berechnung entwickeln](https://github.com/dystonse/dystonse/milestone/3)

### Das haben wir letzte Woche gemacht
 * Langzeitarchivierung von Fahrplandaten in git getestet - geht nur so mäßig, daher erstmal verworfen
 * MacMini mit Debian und Docker eingerichtet, um Raspberry Pi zu ersetzen/ergänzen
 * [docker-compose-Konfiguration](https://github.com/dystonse/dystonse-docker) für Datenbank(-administration) aufgesetzt
 * Angefangen, die Programmiersprache Rust zu lernen
 * [Importer](https://github.com/dystonse/docker-rust-test) in Rust geschrieben, der folgendes tut:
   * Fahrplandaten (aus gtfs) einlesen. Wir haben das auf drei verschiedene Weisen getestet:
     * zunächst mit [`gtfsdb`](https://github.com/OpenTransitTools/gtfsdb) (sehr langsam)
     * dann mit [`gtfs-structures`](https://github.com/rust-transit/gtfs-structure) (133 mal schneller als `gtfsdb`)
     * [`csv`](https://crates.io/crates/csv) selbst parsen (weitere 30 mal schneller als `gtfs-structures`, aber unpraktisch, daher verworfen)
   * Echtzeitdaten (aus gtfs-realtime) einlesen
   * Daten miteinander referenzieren
   * Daten in Datenbank schreiben
 * Definiert und [Notizen](Notizen%20zur%20Prognoseberechnung.md) dazu gemacht, was die Ein- und Ausgabeparameter der Prognose sind

### Das machen wir diese Woche
 * Analyse der bisher gesammelten Daten
 * Software-Komponente für die Prognoseberechnung entwickeln
 * mehr Rust lernen
 
### Das bremst uns gerade
 * Im Zuge der Covid-19-Prävention wurden große Teile des Nahverkehrs eingestellt, dadurch bekommen wir praktisch keine Echzeitdaten mehr. Zum Glück haben wir einige Tage zuvor mit der Aufzeichnung begonnen
 * Das Cross-Compiling mit `docker buildx` schlägt nun [wegen eines bekannten Bugs](https://github.com/dystonse/docker-rust-test#known-problems-with-cross-compiling) fehl, für den es noch keine verfügare Lösung gibt

### Das motiviert uns gerade
 * Rust ist eine spannende Sprache, und sich darin einzuarbeiten ist anspruchsvoll, aber eben auch motivierend


## Woche 3 (Update zum 23. März)
### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1)
 2. [Statistische Analyse der gesammelten Echtzeit-Verspätungs-Daten](https://github.com/dystonse/dystonse/milestone/2)
 3. [Prognose-Berechnung entwickeln](https://github.com/dystonse/dystonse/milestone/3)

### Das haben wir letzte Woche gemacht
 * Langzeitarchivierung von Fahrplandaten in git getestet - geht nur so mäßig, daher erstmal verworfen
 * MacMini mit Debian und Docker eingerichtet, um Raspberry Pi zu ersetzen/ergänzen
 * [docker-compose-Konfiguration](https://github.com/dystonse/dystonse-docker) für Datenbank(-administration) aufgesetzt
 * Angefangen, die Programmiersprache Rust zu lernen
 * [Importer](https://github.com/dystonse/docker-rust-test) in Rust geschrieben, der folgendes tut:
   * Fahrplandaten (aus gtfs) einlesen. Wir haben das auf drei verschiedene Weisen getestet:
     * zunächst mit [`gtfsdb`](https://github.com/OpenTransitTools/gtfsdb) (sehr langsam)
     * dann mit [`gtfs-structures`](https://github.com/rust-transit/gtfs-structure) (133 mal schneller als `gtfsdb`)
     * [`csv`](https://crates.io/crates/csv) selbst parsen (weitere 30 mal schneller als `gtfs-structures`, aber unpraktisch, daher verworfen)
   * Echtzeitdaten (aus gtfs-realtime) einlesen
   * Daten miteinander referenzieren
   * Daten in Datenbank schreiben
 * Definiert und [Notizen](Notizen%20zur%20Prognoseberechnung.md) dazu gemacht, was die Ein- und Ausgabeparameter der Prognose sind

### Das machen wir diese Woche
 * Analyse der bisher gesammelten Daten
 * Software-Komponente für die Prognoseberechnung entwickeln
 * mehr Rust lernen
 
### Das bremst uns gerade
 * Im Zuge der Covid-19-Prävention wurden große Teile des Nahverkehrs eingestellt, dadurch bekommen wir praktisch keine Echzeitdaten mehr. Zum Glück haben wir einige Tage zuvor mit der Aufzeichnung begonnen
 * Das Cross-Compiling mit `docker buildx` schlägt nun [wegen eines bekannten Bugs](https://github.com/dystonse/docker-rust-test#known-problems-with-cross-compiling) fehl, für den es noch keine verfügare Lösung gibt

### Das motiviert uns gerade
 * Rust ist eine spannende Sprache, und sich darin einzuarbeiten ist anspruchsvoll, aber eben auch motivierend


## Woche 2 (Update zum 16. März)
### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1)

### Das haben wir letzte Woche gemacht
 * Weitere Datenquellen gefunden, darunter Echtzeitdaten für 2100 Fahrzeuge in Niedersachsen
 * [Bekannte Datenquellen in einem maschinenlesbaren JSON-Format](datasources.json) niedergeschrieben
 * Übersicht über alle Verkehrsunternehmen Deutschlands gestartet, dazu [ein paar kleine Tools](https://github.com/dystonse/dystonse-tools/tree/master/agencies) geschrieben
 * [Versuche mit `docker buildx`](https://github.com/dystonse/docker-rust-test), um unseren künftigen Rust-Code gleich für mehrere Architekturen (amd64, armv7) zu bauen und zu deployen
 * Einen Raspberry Pi als Versuchsserver mit Docker eingerichtet
 * Mit GitHub Pages einen Blog auf [blog.dystonse.org](https://blog.dystonse.org/) eingerichtet und ersten [Blogpost über Datensammlung](http://blog.dystonse.org/opendata/2020/03/13/datensammlung.html) veröffentlicht
 * Simples Skript zur Aufzeichnung der Echtzeitdaten (alle 2 Minuten) und der Fahrpläne (1 mal täglich) geschrieben und in Betrieb genommen
 * Manuell geprüft, ob die Echtzeitdaten sich mit dem Fahrplan referenzieren lassen (ja, es geht)

### Das machen wir diese Woche
 * Die Daten nicht nur einfach als Datei herunterladen, sondern in Datenbanken speichern
 * Erste statistische Auswertungen über die Daten
 * MacMini in Betrieb nehmen, der den Raspberry Pi unterstützt oder ersetzt
 * Die Sammel- und Analysevorgänge dockerisieren, damit wir sie später leichter auf weitere Datenquellen ausweiten können
 * Zwei Ideen zur speichereffizienten Langzeitarchivierung von Fahrplanversionen ausformulieren und veröffentlichen (wir sind noch nicht sicher, ob wir die je umsetzen werden)
  
### Das bremst uns gerade
 * Fürchterliche Dokumentation von GitHub Pages, Ausfälle bei GitHub (inzwischen behoben)
 * Andere Jobs und private Aufgaben

### Das motiviert uns gerade
 * Dass unser Zuwendungsbescheid nun doch angekommen ist
 * Dass wir endlich eine brauchbare Datenquelle gefunden haben

## Woche 1 (Update zum 9. März)

### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1)

### Das haben wir letzte Woche gemacht
 * Mit Abstand der größte Brocken Arbeit in dieser Woche: Potentielle [Datenquellen](./Datenquellen.md) und [-Formate](./Datenformate.md) für Echtzeitdaten recherchiert.
 * Mit [Jannis](https://github.com/derhuerst) getroffen, der Open Data und Open Source rund um den Berliner Nahverkehr macht
 * Ein kleines [Fotoshooting in der Berliner U-Bahn](https://twitter.com/dystonse/status/1235250055084494849) :)
 * Etwas Finanz- und Papierkram
 * Strukturierte [Notizen](./Notizen.md) gemacht
 * Softwarekomponenten und Datenflüsse [überlegt](./Komponenten.md) und in ein [Diagramm](https://github.com/dystonse/dystonse/blob/master/project-status/Dystonse%20Komponenten.png) gegossen
 * Milestones überarbeitet und [in GitHub eingepflegt](https://github.com/dystonse/dystonse/milestones?direction=asc&sort=title&state=open)
 * Die Lizenz bzw. Nutzungsbedingungen für Echtzeitdaten in Münster [erfragt](https://twitter.com/dystonse/status/1235241688278458369) und erfahren, dass die alles andere als offen sind
 * Auf Twitter nach offenen Daten gefragt und tatsächlich mehrere gute Hinweise bekommen
 * Testweise ein kleines [Docker-Setup](https://github.com/dystonse/gtfs-collector/blob/master/VRN.env) aufgesetzt und eine Zeit lang Fahrplan- und Echtzeit-Daten aus dem VRN erfolgreich aufgezeichnet

### Das machen wir diese Woche
 * Entscheiden, welche Region als erste Testregion in Frage kommt
 * zuverlässige Datensammlung für diese Region vorbereiten
 * Fahrplandaten von [gtfs.de](https://gtfs.de/) evaluieren und in Datenbank importieren

### Das bremst uns gerade
 * Die Unsicherheit, da unser Förderbescheid noch nicht da ist
 * Andere Jobs und private Aufgaben
 * Dass die Informationen darüber, wo es Echtzeitdaten als Open Data gibt, selbst nicht strukturiert und offen zugänglich ist, und generell vieles noch nicht offen ist

### Das motiviert uns gerade
 * Dass es endlich los geht und wir viel gutes Feedback aus der Community (vorallem über Twitter) bekommen
 * Die vielen Ecken und Enden, an denen wir etwas tun können
 * Dass 2024 die nötigen Echtzeitdaten für ganz Deutschland offen sein werden, und wir dann schon die passende Software haben werden

_und hier das Template für künftige Wochen:_

## Woche X (Update zum X. Xxx)
### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1)

### Das haben wir letzte Woche gemacht
 * ?

### Das machen wir diese Woche
 * ?
 
### Das bremst uns gerade
 * ?

### Das motiviert uns gerade
 * ?
