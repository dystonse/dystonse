# Arten von Echtzeitdaten
## Gemäß Standards
### SIRI
SIRI allows pairs of server computers to exchange structured real-time information about schedules, vehicles, and connections, together with general informational messages related to the operation of the services. The information can be used for many different purposes, for example:

 * To provide real time-departure from stop information for display on stops, internet and mobile delivery systems;
 * To provide real-time progress information about individual vehicles;
 * To manage the movement of buses roaming between areas covered by different servers;
 * To manage the synchronisation of guaranteed connections between fetcher and feeder services;
 * To exchange planned and real-time timetable updates;
 * To distribute status messages about the operation of the services;
 * To provide performance information to operational history and other management systems.

[source](http://www.transmodel-cen.eu/standards/siri/)

### GTFS Realtime
Ein `TripUpdate` enthält einen `delay` in Sekunden, und eine Menge von `stop_time_update` für vergangene und/oder künftige Halteplukte. 

Jedes `stop_time_update` hat 1-2 `StopTimeEvent`s, für Ankunft und/oder Abfahrt. Diese haben jeweils `time` (absolute Zeit inkl. `delay`) und/oder `delay`, sowie `uncertainty`. Letztere ist nicht genau definiert.

Außerdem können `VehiclePositions` vorhanden sein, die einem Fahrzeug zu einer bestimmten Zeit eine Position und weitere Statusfelder zuordnet. Die `Position` besteht dabei nicht nur aus `latitude` und `longitude`, sondern enthält u.a. auch Geschwindigkeit und Richtung.

[Quelle](https://developers.google.com/transit/gtfs-realtime/reference/#message-tripupdate)

### Transmodel
Das ist wirklich komplex und da blickt keiner durch.

## Gemäß realer Quellen
### VBB Echtzeitkarte
Eine Menge von Fahrzeugupdates mit diesen Feldern ([April 2017](https://github.com/dystonse/dystonse-tools/blob/master/src/main/java/net/dystonse/tools/Import.java#L135) reverse engineered):

 * `i` = `compound_id`
 * `c` = `productclass`
 * `d` = `d`
 * `n` = `name`
 * `l` = `destination`
 * `x,y` = `location`
 * `rt` = `delay` in Minuten

Es müsste noch analysiert werden, inwiefern die `location` aus GPS-Daten stammt oder nur aus den Routendaten errechnet ist. Auch wie der `delay` sich berechnet ist unklar. Immerhin kann dieser `null` sein und ist somit von `0` zu unterscheiden.

### HAFAS
???

### Münster
Laut Dokumentation bietet die API nur Positionen und keine Verspätungsinformation. Wie wir am 4. März erfahren haben, werden aber auch Verspätungsinformationen in Sekunden (nicht auf Minuten gerundet!) mit übertragen. Unsere bisherige Planung geht noch davon aus, dass diese Daten fehlen.

Beispieldaten aus dem Webinterface:

```
{
    "visfahrplanlagezst": "4.3.2020, 18:20:18",
    "linienid": "33",
    "nachhst": "4587101",
    "fahrtstatus": "Ist",
    "ankunftziel": "2020-03-04T18:32:00+01:00",
    "richtungstext": "Ringlinie",
    "sequenz": 19,
    "delay": 176,
    "linientext": "33",
    "zielhst": "4100001",
    "fahrtbezeichner": "94100041018001",
    "richtungsid": "1",
    "fahrzeugid": "5122",
    "starthst": "4100001",
    "betriebstag": "2020-03-04",
    "abfahrtstart": "2020-03-04T17:50:00+01:00",
    "akthst": "4549101",
    "operation": "MODIFY"
}
```

### Zwischenfazit
Im Wesentlichen gehören alle Echtzeitdaten in einer dieser drei Kategorien / Formate:
 * Verspätung eines Fahrzeuges zu einer bestimmten Zeit
 * Ort eines Fahrzeuges zu einer bestimmten Zeit
 * Ankunftsprognose eines Fahrzeuges für einen oder mehrere zukünftige Halte von einer bestimmten Zeit

Jedes Format lässt sich in etwa in die anderen Formate konvertieren, mit gewissen Ungenauigkeiten. Unter Umständen wurden die Daten, die wir erhalten, auch schonmal konvertiert.

Folgende Ebenen / Komponenten:
 * Anfragen von Daten in 1-3 der oben genannten Formate und direktes eintragen in eine Datenbank, die all diese Formate unterstützt
 * Konvertieren aller Daten in ein gemeinsames Format und speichern in einer weiteren Datenbank
 * Berechnen von Prognosen als Wahrscheinlichkeitsverteilung und speichern in einer weiteren Datenbank

