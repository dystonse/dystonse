# Notizen
_hier sammeln wir allgemeine Notizen, die (noch) in keine gesonderte Datei gehören._

## Formate
* NeTEx: https://www.vdv.de/netex.aspx
* Transmodel: http://www.transmodel-cen.eu/

## Tools
* Verwaltung von vielen GTFS-Feeds: https://github.com/geops/gtfsman
* Exakte Shapes aus GTFS und OSM erzeugen: https://github.com/ad-freiburg/pfaedle
* GTFS in Datenbanken packen: https://github.com/OpenTransitTools/gtfsdb
* GTFSr in Datenbanken packen: https://github.com/mattwigway/gtfsrdb

## Personen
* Pad mit Leuten vom 35c3: https://pad.okfn.de/p/35c3mobilitaet (angeblich gibt es ein Slack? OKF betreibt das wohl)
* Weitere Projekte von Patrick Brosi https://www.patrickbrosi.de/de/projects/
* Katja Diehl, Women in Mobility

## Rust
* async / await ist seit November 2019 endlich stable und kann benutzt werden
* Rust kann in WebAssembly kompiliert werden und im Browser laufen, mit Java Script verknüpft werden. So könnten wir Teile unseres Codes auf dem Server oder im Browser laufen lassen, ohne sie doppelt zu schreiben 

## Architektur
Ein paar lose Ideen zu Architektur und welche Features möglich wären, wenn wir auch direkt auf dem Endgerät Suchen berechnen könnten

Wir können einige Kernklassen in Rust schreiben, die wir im Server, in Apps und auf der Webseite nutzen können. Das würde es ermöglichen, beliebige Berechnungen zwischen diesen Systemen hin und her zu schieben. Nützlich ist es auch, um Arbeit zwischen mehreren Server umzuschichten.

Die Idee dabei wäre, dass eine Instanz auf einem reduzierten Datensatz laufen kann, der nur Fahrten enthält, die voraussichtlich relevant sind. Sie kann das Aktualisierungen für genau diese Fahrten erhalten, die ggf. kompakter sind als die Ergebnisse der Berechnungen, die damit ausgeführt werden.

Theoretisch könnte sogar das GPS des Mobilgerätes und/oder des Zuges genutzt werden, um die Verspätungsinformation des eigenen Fahrzeugs lokal zu updaten, und Nuter_innen könnten selbst Updates eingeben, die sie z.B. aus Durchsagen erhalten haben.

Wenn zwei Instanzen sich darüber einig sind, welche Fahrten betrachtet werden, dann kann ein Update sehr klein Ausfallen. "Läuft alles nach Prognose" als Standardfall kann prinzipiell in einem Bit kodiert werden, auch wenn die Information nur mit einem Zeitstempel wirklich nützlich ist. Gegenüber einer fehlenden Information ist da ein realer Zugewinn, der die Prognosen ab da genauer macht.

Die Einheit, die aus der letzten Position / Verspätung, deren Zeit und anderen Metadaten Prognosen erstellt, kann auch beliebig komplex sein, sowohl in ihrer Berechnungsweise als auch in der Menge der Daten, die sie zu Grunde legt. 

(An der Stelle sei gesagt, dass wir für  manche Fahrzeuge nur Verpätungen / nur Prognosen / nur Positionen aus der API bekommen, und dass wir die ggf. ineinander umrechnen müssen)

## Sonstiges
Idee: Zweistufige Heuristik. Der Wahrscheinlichkeitsbasierte Algorithmus nutze als Heuristik einen Best-Case-A*, und der nutzt wiederum als Heuristik eine Luftlinienberechnung. Der sog. Best-Case-A* nutzt für jeden Streckenabschnitt die kürzeste Reisezeit, die dort jemals gemessen wurde. Diese mittlere Heuristik wäre teuerer, aber würde vermutlich sehr viel Rechenzeit bei der eigentlichen Suche sparen.

Idee: Unzuverlässigkeit der User mit einberechnen. Fehler wie zu frühes / zu spätes Aussteigen oder das Einsteigen in das falsche Verkehrsmittel passieren. Ein Algorithmus, der eh schon wahrscheinlichkeitsbasiert ist, kann das mit einberechnen. Dadurch würden Routen priorisiert werden, bei denen Fehler per se unwahrscheinlicher sind, oder bei denen Fehler weniger schlechte Konsequenzen haben. Inspiriert von [diesem Tweet](https://twitter.com/maussagenlogik/status/1235659894361124864).