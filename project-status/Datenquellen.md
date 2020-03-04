# Datenquellen

## (Soll-)Fahrpläne

### Konkrete Quellen
* [Deutschlandweites GTFS aus NeTEx von Patrick Brosi](https://gtfs.de/)
* [Weltweite GTFS-Feeds, filterbar nach Echtzeit-Daten](https://tracker.geops.de/feeds/)
* [Validierte GTFS-Feeds für Deutschland](https://gtfs.mfdz.de/)
* Die Bahn hat wohl zwei Datenportale:
  * [Open-Data-Portal](https://data.deutschebahn.com/)
  * [OPEN API Portal]( https://developer.deutschebahn.com/store/)
* [Meta-Übersicht der DB über Datenquellen](https://web.archive.org/web/20200302221530/https://gobeta.de/projekte/dataportale/)

## (Ist-)Echtzeitdaten

### Konkrete Quellen
* Berlin:
  * [VBB-Echtzeitkarte existiert noch](http://fahrinfo.vbb.de/bin/help.exe/dn?L=vs_mobilitymap&tpl=fullmap&tabApp=show)
* Münster:
  * Echtzeitpositionen der Busse mit [Karte](http://api.busradar.conterra.de/demo/) und [API](http://api.busradar.conterra.de/) (war seit Januar kaputt, geht seit 4. März wieder)
* Deutsche Bahn:
  * [Zugverfolgung.com hat Echtzeitdaten für u.a. DB-Züge)[https://www.zugverfolgung.com/db-deutsche-bahn]
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

### Wegen Echtzeit-Datenzugriff anschreiben
* VBB
* BVG
* DB
* BSVG
* DELFI
* Conterra / Stadtwerke Münster
* Regionalverband Großraum Braunschweig
* ggf. die 19 Städte mit dem "init"-System

## Hintergrund-Informationen

### Zur Deutschen Bahn
* Die "Echtzeitpositionen" der DB wurden Ende 2018 abgestellt, da sie eh nie realistisch waren, wie die Bahn [selbst sagt](https://web.archive.org/web/20190417012918/https://www.bahn.de/p/view/service/mobile/zugradar.shtml).
* [Abfrage von Position und Geschwindigkeit, während man im WLAN des Zugs eingeloggt ist](https://hannover.ccc.de/~nexus/dbwifi/)
* [Podcast von "EinfachBahn", was wohl einer Steller innerhalb der DB ist, u.a. zu open data](https://open.spotify.com/show/3fIeX7IkQmfViIu1cj34SU)

### Zu anderen Anbietern
* [Übersicht über Open Data, Openwashing und NoData von statischem GTFS in Deutschland](https://rettedeinennahverkehr.de/)
* [Slides über "Zentrale Bereitstellung EU-weiter multimodaler Reiseinformationsdienste"](https://okfn.de/files/blog/2018/01/BMVI_Dialogforum_am_31-01-18.pdf)
* [DELFI e.V.](https://www.delfi.de/) als Akteur bei den Nationalen Zugangspunkten (?)
* [Open Data ÖPNV](https://www.opendata-oepnv.de/ht/de/willkommen)
* Prognostiziertes Fartaufkommen für [Berlin](https://www.mcloud.de/web/guest/suche/-/results/detail/AD4ACF34-F801-4F0F-8EED-E9F30788E26C?_mcloudsearchportlet_backURL=https%3A%2F%2Fwww.mcloud.de%2Fweb%2Fguest%2Fsuche%2F-%2Fresults%2FsearchAction%3F_mcloudsearchportlet_currentAggs%3Dextras.subgroups%253A%2522railway%2522%26_mcloudsearchportlet_page%3D0%26_mcloudsearchportlet_sort%3Dlatest), [München](https://www.mcloud.de/web/guest/suche/-/results/detail/1BA3649D-D1FB-4409-9023-0EBE21B35292?_mcloudsearchportlet_backURL=https%3A%2F%2Fwww.mcloud.de%2Fweb%2Fguest%2Fsuche%2F-%2Fresults%2FsearchAction%3F_mcloudsearchportlet_currentAggs%3Dextras.subgroups%253A%2522railway%2522%26_mcloudsearchportlet_page%3D0%26_mcloudsearchportlet_sort%3Dlatest), [Duisburg](https://www.mcloud.de/web/guest/suche/-/results/detail/3F3B46C3-C72A-4DB7-8B2D-D20C5375DF51?_mcloudsearchportlet_backURL=https%3A%2F%2Fwww.mcloud.de%2Fweb%2Fguest%2Fsuche%2F-%2Fresults%2FsearchAction%3F_mcloudsearchportlet_currentAggs%3Dextras.subgroups%253A%2522railway%2522%26_mcloudsearchportlet_page%3D0%26_mcloudsearchportlet_sort%3Dlatest)
 * [Koordinaten der Zugangsmöglichkeiten zu Stationen](https://www.mcloud.de/web/guest/suche/-/results/detail/_mcloudde_koordinatenderzugangsmglichkeitenzustationen?_mcloudsearchportlet_backURL=https%3A%2F%2Fwww.mcloud.de%2Fweb%2Fguest%2Fsuche%2F-%2Fresults%2FsearchAction%3F_mcloudsearchportlet_currentAggs%3Dextras.subgroups%253A%2522railway%2522%26_mcloudsearchportlet_page%3D3%26_mcloudsearchportlet_sort%3Dlatest)

# OpenStreetMap (OSM)
Bei der [geofrabrik](https://download.geofabrik.de/europe/germany.html) können wir Dumps und Diffs herunter laden. Berlin könnten wir jedes Mal neu runter laden, sind nur 55 MB. Deutschland sind 4GB mit 4MB an täglichen Diffs, die wir mit [Osmosis](https://wiki.openstreetmap.org/wiki/Osmosis) oder [Osmium](https://osmcode.org/osmium-tool/) verarbeiten könnten.

[Pfaedle](https://github.com/ad-freiburg/pfaedle) spricht derzeit nur XML, das könnten wir uns aber aus unserer DB heraus exportieren.

Vermutlich werden wir noch andere Anwendungen haben, bei denen es gut ist, OSM lokal abfragbar da zu haben. Es gibt bereits fertige Lösungen mit Docker ([nur Daten](https://github.com/kartoza/docker-osm), [Tileserver](https://github.com/Overv/openstreetmap-tile-server/blob/master/README.md)), um sowas immer aktuell zu haben.