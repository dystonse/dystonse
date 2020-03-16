# Datenquellen

_Im Moment erreichen uns täglich neue Hinweise auf verfügbare und (halb-)offene Datenquellen für Echtzeitinfos. Wir kommen im Moment nicht damit hinterher, das gesamte Dokument aktuell und aufgeräumt zu halten. Am ehesten aktuell ist die [Tabelle](#vergleich-von-echtzeit-datenquellen) weiter unten._

## (Soll-)Fahrpläne

### Konkrete Quellen
* [Deutschlandweites GTFS aus NeTEx von Patrick Brosi](https://gtfs.de/)
* [Weltweite GTFS-Feeds, filterbar nach Echtzeit-Daten](https://tracker.geops.de/feeds/)
* [Validierte GTFS-Feeds für Deutschland](https://gtfs.mfdz.de/)
* Die Bahn hat wohl zwei Datenportale:
  * [Open-Data-Portal](https://data.deutschebahn.com/)
  * [OPEN API Portal]( https://developer.deutschebahn.com/store/)
* [Meta-Übersicht der DB über Datenquellen](https://gobeta.de/projekte/dataportale/)
* [Portal für statische Daten mehrerer Verbünde](https://www.opendata-oepnv.de/ht/de/willkommen) - heißt Open Data, ist aber leider nicht alles Open im eigentlichen Sinne
* [mcloud -  Rechercheplattform zu offenen Daten aus dem Bereich Mobilität und angrenzender Themen des BMVI](https://www.mcloud.de/web/guest/suche/-/results/searchAction?_mcloudsearchportlet_aggsChoice=extras.subgroups%3A%22railway%22)

## (Ist-)Echtzeitdaten

### Konkrete Quellen
* Berlin:
  * [VBB-Echtzeitkarte existiert noch](http://fahrinfo.vbb.de/bin/help.exe/dn?L=vs_mobilitymap&tpl=fullmap&tabApp=show)
* Münster:
  * Echtzeitpositionen der Busse mit [Karte](http://api.busradar.conterra.de/demo/) und [API](http://api.busradar.conterra.de/) (war seit Januar kaputt, geht seit 4. März wieder)
  * Im Oktober 2017 haben die Stadtwerke Münster [in einem Kommentar auf ihrer Website angekündigt](https://www.stadtwerke-muenster.de/blog/verkehr/eine-anekdote-wie-wir-zu-fis2go-kamen/), eine API für einen Hackathon zur Verfügung zu stellen.
  * Im Februar 2018 hat Felix Wöstmann über [Frag den Staat](https://fragdenstaat.de/anfrage/api-der-bus-echtzeitauskunft/) die Stadtwerke nach der API-Dokumentation gefragt. Die Antwortete, dass die Dokumentation nicht öffentlich werde, aber die Schnittstelle genutzt werden darf
  * Wir haben mal [auf Twitter](https://twitter.com/dystonse/status/1235241688278458369) nachgefragt, wie da die Bedinungen sind
  * [Artikel über die Datenqualität](http://www.stadtwerke-muenster.de/blog/verkehr/wie-aus-einer-minute-drei-werden-koennen-echtzeitauskunft-und-ihre-grenzen/) und ein [Update von 2015](https://www.stadtwerke-muenster.de/blog/verkehr/von-analog-zu-digital-fis-verbessert/) dazu
* Ulm
  * Echtzeit-Abfahrtsdaten für Ulm gibt es von DING, [dokumentiert von der Fachschaft Elektrotechnik](http://bus.fs-et.de/bus/info.html). In den [XML-Daten](http://www.ding.eu/ding2/XML_DM_REQUEST?laguage=de&typeInfo_dm=stopID&nameInfo_dm=9001240&deleteAssignedStops_dm=1&useRealtime=1&mode=direct) findet sich kein Hinweis auf Verspätungsangaben.
  * Diverse Projekte dazu [bei UlmAPI](https://github.com/UlmAPI)
* Nürmberg
  * [Beispielanfrage am Hbf](https://start.vag.de/dm/api/v1/abfahrten/VGN/510) (weil die URL etwas hakelig zusammenzubauen ist)
* Deutsche Bahn:
  * [Zugverfolgung.com hat Echtzeitdaten für u.a. DB-Züge](https://www.zugverfolgung.com/db-deutsche-bahn)
  * [Die Deutsche Bahn hat ihr Zugradar noch online, aber ihre Google Maps Rechnung nicht bezahlt](http://www.apps-bahn.de/bin/livemap/query-livemap.exe/dn?L=vs_livefahrplan&livemap=yes)
  * [Jannis' Hafas-Client kann das DB-Radar abfragen](https://github.com/public-transport/hafas-client/blob/5/docs/radar.md)
* Schweiz:
  * sind die Echtzeitdaten angeblich per Gesetz offen und als Stream verfügbar (Quelle vergessen)
  * [Tagesaktuelle Downloads und ein Archiv seit Janaur 2018](https://opentransportdata.swiss/de/dataset/istdaten)
  * [Liste der Transportunternehmen mit Echtzeitdaten](https://opentransportdata.swiss/de/dataset/go-realtime/resource/3b57792a-1679-4b97-8c9b-f06faa1c9cf6)
  * [GTFS-RT Endpoint](https://api.opentransportdata.swiss/gtfs-rt) mit [Nutzungsbedingungen und Anmeldung](https://opentransportdata.swiss/de/terms-of-use/)

### Weitere Informationen
* Europäischer Standard für Echtzeitdaten: [SIRI](https://de.wikipedia.org/wiki/Service_Interface_for_Real_Time_Information), mit zwei dokumentierten Implementierungen:
  * [MENTZ Datensysteme in München](https://www.mentz.net/loesungen/efa/echtzeitdaten/) ("Die Elektronische Fahrplanauskunft von MENTZ bezieht deshalb Echtzeitdaten von Anfang an ins Routing ein.")
  * [init, betreibt Infrastruktur in etwa 19 deutschen Städten](https://www.initse.com/dede/projekte.html)
* [Vernichtender Artikel von 2012 über die Echtzeitdaten in Berlin](https://signalarchiv.de/Meldungen/10000634)
* Braunschweig bekommt bis 2022 überall Echtzeitanzeigen, [Artikel mit Kontaktdaten dazu](https://www.regionalverband-braunschweig.de/echtzeit/)
* [DELFI e.V. hat im März 2019 Echtzeitdaten in D betrachtet und Handlungsbedarf geäußert](https://www.delfi.de/de/download/?f=20190331-finale_kurzfassung_kurzbericht_fops_dds_01-00.pdf)
* DELFI nennt für Echtzeitdaten die TRIAS-Schnittstelle (Travellers' Reaktime Information and Advisory Standard)
* [Linkliste "BahnData" von 2016](https://github.com/highsource/bahndata)
* [Ausschreibung zur Versorgung Niedersachsens mit Echtzeit-Daten](https://ausschreibungen-deutschland.de/561606_Erweiterung_der_landesweiten_Datendrehscheibe_Niedersachsen_2019_Bremen)
* [Förderprogramm Saubere Luft 2017-2020](https://www.bmvi.de/SharedDocs/DE/Artikel/G/sofortprogramm-saubere-luft-2017-2020.html) mit dem unter anderem Open Data des VBN gefördert wurde. [Übersicht über geförderte Maßnamen](https://www.bmvi.de/SharedDocs/DE/Anlage/K/presse/foerderbescheide-digitalisierung-kommunale-verkehrssysteme.pdf?__blob=publicationFile).
* [Nahverkehrsplan 2020](https://www.regionalverband-braunschweig.de/fileadmin/user_upload/05_Veroeffentlichungen/Regionalverkehr/NVP_2020/NVP2020_Beschlussfassung.pdf) für den Großraum Braunschweig

### Wegen Echtzeit-Datenzugriff anschreiben
* VBB
* BVG
* DB
* BSVG
* DELFI
* Conterra / Stadtwerke Münster
* Regionalverband Großraum Braunschweig
* ggf. die 19 Städte mit dem "init"-System

### Vergleich von Echtzeit-Datenquellen
| Ort                         | Verkehrsmittel                                      | Open Data          | Format                           | Aktuelle Verspätung auf Strecke                     | Prognose                    | Position | Vorteile                                                                                        | Nachteile                                                            |
|-----------------------------|-----------------------------------------------------|--------------------|----------------------------------|-----------------------------------------------------|-----------------------------|----------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Verbund Rhein-Neckar        | Bus, Tram, evtl. weitere                            | [Ja][5]            | GTFS-Realtime                    | Ja                                                  | Ja                          | Nein     | Bisher erste bekannte offene Echtzeitdaten                                                      | Stream enthält evtl. nur Infos zu 100 von 1380 Fahrzeugen            |
| Nürnberg                    | Bus, Tram, U-Bahn                                   | Ja [CC BY 4.0][6]  | [PULS REST][7]                   | Nein                                                | Ja (sekundengenau)          | Nein     | Bisher erste bekannte offene Echtzeitdaten                                                      |                                                                      |
| Niedersachsen und Bremen    | ?                                                   | [CC BY 4.0][12]    | GTFS-Realtime                    | Nein                                                | Ja (sekundengenau)          | Nein     | Sehr großer Datensatz mit über 2000 Fahrzeugen                                                  | Fahrpläne für Schleswig-Holstein mit [eigener Lizenz][13]            |
| Berlin                      | Diverser Nahverkehr (Tram, S-Bahn, U-Bahn, Bus)     | Nein               | HTTP-API / Json                  | Ja                                                  | Über andere API             | Ja       | Verfügbar, viel statisches Open Data                                                            | durch hohe Taktdichte nicht so relevant                              |
| Bonn / VRS                  | Bus, Tram, Stadtbahn                                | [Jein][10]         | GTFS-Realtime                    | ?                                                   | ?                           | ?        | [Offen für innovative Vorhaben][14], aber...                                                    | [Statistik verboten][10], Begrenzung auf 10K Anfragen täglich        |
| Braunschweig                | Tram und Bus                                        | ?                  | ?                                | ?                                                   | Müsste (bald) vorliegen [4] | ?        | Gut für lokales Testen                                                                          | Evtl. Gar nicht verfügbar                                            |
| Münster                     | Bus                                                 | [Nein][1]          | GTFS-Realtim, Rest, Websocket    | Ja                                                  | Nein                        | Ja       | Evtl. open data (ist angefragt), relativ gut für lokale Tests                                   | nur Busse                                                            |
| Ulm                         | Bus, Straßenbahn, evtl. Bedarfsverkehr              | [Bald][2]          | ?                                | Ja                                                  | Nein                        | Ja       | Open Data für die Zukunft festgeschrieben                                                       | Noch nicht verfügbar                                                 |
| Stuttgart                   | Bus, Stadtbahn, S-Bahn, Zahnradbahn, Standseilbahn  | [Bald][3]          | GTFS-Realtime                    | Ja                                                  | Nein                        | Ja       | evtl. erste deutsche Stadt mit GTFS-Realtime                                                    | Noch nicht verfügbar                                                 |
| Herrenberg                  | Bus                                                 | ?                  | ?                                | Nein                                                | Nein                        | [Ja][3]  |                                                                                                 |                                                                      |
| Deutschland                 | Fernzüge, Regionalzüge                              | Nein               | HAFAS-API und JS-Wrapper in FPTF | Nicht über HAFAS-Radar, aber über record-hafas-data | Ja                          | Ja       | Lange Taktzeiten für viel Relevant, große Zielgruppe, Community hat viel Erfahrung mit den APIs | Kein Open Data für Echtzeit                                          |
| [Wien][11]                  | Bus, Tram, U-Bahn                                   | Ja                 | JSON                             | Nein                                                | Ja                          | Nein     |                                                                                                 | Eigenes Format, wenn auch gut dokumentiert                           |
| Schweiz                     | Verschiedene Züge (?)                               | Ja                 | GTFS-Realtime                    | ?                                                   | ?                           | ?        | Realtime verfügbar und open data                                                                | Kein lokaler Test, kaum echte Relevanz                               |
| Vereinigtes Königreich      | Zug, U-Bahn, Bus                                    | Ja, [limitiert][8] | GTFS / JSON                      | ?                                                   | Ja                          | ?        |                                                                                                 | Nur bis zu 30k Request pro Monat kostenlos                           |
| Diverse Städte in den USA   | Nahverkehr                                          | Ja                 | GTFS-Realtime                    | ?                                                   | ?                           | ?        | Realtime verfügbar und open data, Praxiserprobt                                                 | Kein lokaler Test, keine echte Relevanz                              |

[1]: https://twitter.com/codeformuenster/status/1235273236360900608
[2]: https://twitter.com/verschwoerhaus/status/1235529198078513154
[3]: https://twitter.com/mfdz_de/status/1235548411908288515
[4]: https://www.regionalverband-braunschweig.de/echtzeit/
[5]: https://www.vrn.de/service/entwickler/gtfs/index.html
[6]: https://opendata.vag.de/dataset/api-echtzeitauskunft
[7]: https://opendata.vag.de/dataset/1db11564-3aa7-458f-9add-7907b434d052/resource/bbf11225-87cc-4abb-bf4b-1a7e2012aaf5/download/schnittstellenbeschreibung-puls-web-api-v1.0.4.pdf
[8]: https://www.transportapi.com/
[9]: https://opendata.bonn.de/dataset/ist-daten-bus-und-bahn-%C3%B6pnv-realtime
[10]: https://www.vrs.de/fileadmin/Dateien/api/NutzervereinbarungODOS.pdf
[11]: https://opendata.guru/news/u-bahn-linie-d-nach-nussdorf-kommt-heute-28-sekunden-spaeter/
[12]: https://www.vbn.de/service/entwicklerinfos/
[13]: https://www.connect-info.net/opendata/OpenData-AGB-NahSh.pdf
[14]: https://www.vrs.de/fahren/fahrplanauskunft/opendata-/-openservice

## Hintergrund-Informationen
* [Umfangreiche FAQ zu Open Data im Nahverkehr von 2015](https://github.com/UlmApi/beyondtransit/blob/gh-pages/evu-daten-faq.md)
* [Definition offener Daten](http://opendefinition.org/od/2.1/de/)

### Zur Deutschen Bahn
* Die "Echtzeitpositionen" der DB wurden Ende 2018 abgestellt, da sie eh nie realistisch waren, wie die Bahn [selbst sagt](https://web.archive.org/web/20190417012918/https://www.bahn.de/p/view/service/mobile/zugradar.shtml).
* [Abfrage von Position und Geschwindigkeit, während man im WLAN des Zugs eingeloggt ist](https://hannover.ccc.de/~nexus/dbwifi/)
* [Podcast von "EinfachBahn", was wohl eine Stelle innerhalb der DB ist, u.a. zu open data](https://open.spotify.com/show/3fIeX7IkQmfViIu1cj34SU)

### Zu anderen Anbietern
* [Übersicht über Open Data, Openwashing und NoData von statischem GTFS in Deutschland](https://rettedeinennahverkehr.de/)
* [Slides über "Zentrale Bereitstellung EU-weiter multimodaler Reiseinformationsdienste"](https://okfn.de/files/blog/2018/01/BMVI_Dialogforum_am_31-01-18.pdf)
* [DELFI e.V.](https://www.delfi.de/) als Akteur bei den Nationalen Zugangspunkten (?)
* [Open Data ÖPNV](https://www.opendata-oepnv.de/ht/de/willkommen)
* Prognostiziertes Fartaufkommen für [Berlin](https://www.mcloud.de/web/guest/suche/-/results/detail/AD4ACF34-F801-4F0F-8EED-E9F30788E26C?_mcloudsearchportlet_backURL=https%3A%2F%2Fwww.mcloud.de%2Fweb%2Fguest%2Fsuche%2F-%2Fresults%2FsearchAction%3F_mcloudsearchportlet_currentAggs%3Dextras.subgroups%253A%2522railway%2522%26_mcloudsearchportlet_page%3D0%26_mcloudsearchportlet_sort%3Dlatest), [München](https://www.mcloud.de/web/guest/suche/-/results/detail/1BA3649D-D1FB-4409-9023-0EBE21B35292?_mcloudsearchportlet_backURL=https%3A%2F%2Fwww.mcloud.de%2Fweb%2Fguest%2Fsuche%2F-%2Fresults%2FsearchAction%3F_mcloudsearchportlet_currentAggs%3Dextras.subgroups%253A%2522railway%2522%26_mcloudsearchportlet_page%3D0%26_mcloudsearchportlet_sort%3Dlatest), [Duisburg](https://www.mcloud.de/web/guest/suche/-/results/detail/3F3B46C3-C72A-4DB7-8B2D-D20C5375DF51?_mcloudsearchportlet_backURL=https%3A%2F%2Fwww.mcloud.de%2Fweb%2Fguest%2Fsuche%2F-%2Fresults%2FsearchAction%3F_mcloudsearchportlet_currentAggs%3Dextras.subgroups%253A%2522railway%2522%26_mcloudsearchportlet_page%3D0%26_mcloudsearchportlet_sort%3Dlatest)
* [Koordinaten der Zugangsmöglichkeiten zu Stationen](https://www.mcloud.de/web/guest/suche/-/results/detail/_mcloudde_koordinatenderzugangsmglichkeitenzustationen?_mcloudsearchportlet_backURL=https%3A%2F%2Fwww.mcloud.de%2Fweb%2Fguest%2Fsuche%2F-%2Fresults%2FsearchAction%3F_mcloudsearchportlet_currentAggs%3Dextras.subgroups%253A%2522railway%2522%26_mcloudsearchportlet_page%3D3%26_mcloudsearchportlet_sort%3Dlatest)
* [Lange Liste mit Datenquellen, Tools, Einführungskursen zu GTFS, etc.](https://git.digitaltransport4africa.org/learn/tools/awesome-transit)

# OpenStreetMap (OSM)
Bei der [geofabrik](https://download.geofabrik.de/europe/germany.html) können wir Dumps und Diffs herunter laden. Berlin könnten wir jedes Mal neu runter laden, sind nur 55 MB. Deutschland sind 4GB mit 4MB an täglichen Diffs, die wir mit [Osmosis](https://wiki.openstreetmap.org/wiki/Osmosis) oder [Osmium](https://osmcode.org/osmium-tool/) verarbeiten könnten.

[Pfaedle](https://github.com/ad-freiburg/pfaedle) spricht derzeit nur XML, das könnten wir uns aber aus unserer DB heraus exportieren.

Vermutlich werden wir noch andere Anwendungen haben, bei denen es gut ist, OSM lokal abfragbar da zu haben. Es gibt bereits fertige Lösungen mit Docker ([nur Daten](https://github.com/kartoza/docker-osm), [Tileserver](https://github.com/Overv/openstreetmap-tile-server/blob/master/README.md)), um sowas immer aktuell zu haben.

# Maschinenlesbare Datenverzeichnisse
Wir haben unsere Daten in ein eigenes JSON-Format gegossen, nicht wissend, dass es auch schon [eine Spezifikation](https://github.com/transitland/distributed-mobility-feed-registry) dafür gibt.