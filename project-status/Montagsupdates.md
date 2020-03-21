# Montagsupdates
_Im Rahmen der Projektförderung durch den [Prototype Fund](https://prototypefund.de) berichten wir wöchentlich über unseren Fortschritt, neueste Updates zuerst._


## Woche 3 (Update zum 23. März) ENTWURF, DA DIE WOCHE NOCH NICHT VORBEI IST
### An diesen Milestones arbeiten wir gerade
 1. [Kontinuierliche Verspätungs-Datensammlung planen, aufbauen und betreiben](https://github.com/dystonse/dystonse/milestone/1)
 2. [Statistische Analyse der gesammelten Echtzeit-Verspätungs-Daten](https://github.com/dystonse/dystonse/milestone/2)
 3. [Prognose-Berechnung entwickeln](https://github.com/dystonse/dystonse/milestone/3)

### Das haben wir letzte Woche gemacht
 * Langzeitarchivierung von Fahrplandaten in git getestet - geht nur so mäßig, daher erstmal verworfen
 * MacMini mit Debian und Docker eingerichtet, um Raspberry Pi zu ersetzen/ergänzen
 * Fahrplandaten mit `gtfsdb` in eine Datenbank geladen - ist viel zu langsam für den ernsthaften Ansatz
 * Angefangen, die Programmiersprache Rust zu lernen
 * Fahrplandaten in Rust mit `gtfs-structures` gelesen, was 133 mal schneller ist als `gtfsdb`
 * Fahrplandaten in Rust mit eigenem `csv`-basierten Parser gelesen, was nochmals 30 mal schneller ist `gtfs-structures`
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
