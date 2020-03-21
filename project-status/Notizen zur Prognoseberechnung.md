# Notizen zur Prognoseberechnung

### Parameter zum Aufruf der Prognose:
- Datum
- Uhrzeit
- Fahrzeug/Linie/trip/...?
- Richtung
- Haltestelle
- Ankunft oder Abfahrt
- Angenommene fiktive Verspätung an einer bestimmten früheren Haltestelle (für bedingte Berechnungen)

### Ausgabewert:
- kumulierte Wahrscheinlichkeitsverteilung für die tatsächliche Ankunfts-/Abfahrtszeit: Funktion p von t im Bereich t1 bis t2 mit p(t1)=0 und p(t2)=1 bzw. p(t2)=lim(p(t))für t-> +unendlich
- dargestellt durch t1 und t2 sowie ein Array von p(t)-werten in einem global definierten gleichmäßigen Abstand (z.B. 30 Sekunden)
- oder durch ein Array von (t,p(t))-Paaren mit ggf. ungleichmäßigen t-Abständen (z.B. durch Douglas-Peucker-Approximation berechnet)
- alternativ: Funktion als Approximation berechnen (z.B. Spline-Interpolation oder Polynomapproximation. Wichtig: die Funktion muss monoton steigend bleiben!) und Funktions-Koeffizienten speichern (weniger Speicherplatzbedarf und besser für Berechnungen).
- welche Variante effizienter ist, muss noch getestet werden.

### Konfigurationsparameter:
- zeitlicher Abstand der Sample-Punkte der Ausgabe
- Gewichtung der verschiedenen Einflussfaktoren

### Zusätzliche Daten, die während der Berechnung angefragt werden:
- Fahrplandaten für die betrachtete Fahrt
- Verspätungswerte der gleichen Fahrt an früheren Tagen
- Verspätungswerte des gleichen Verkehrsmittels am gleichen Ort zu anderen Uhrzeiten
- durchschnittliche Verspätungswerte des gleichen Verkehrsmittels
- Echtzeit-Verspätungsprognose der betrachteten Fahrt für die betrachtete Haltestelle
- Echtzeit-Verspätung der betrachteten Fahrt an vorherigen Haltestellen
- vergangene Verspätungen der gleichen Linie an vorherigen Haltestellen und der betrachteten (Aufholung?)
- evtl. Abfahrtszeiten/-intervalle laut Fahrplan, falls mehrere Fahrten auf der gleichen Linie berücksichtigt werden sollen
- evtl. Echtzeit-Verspätung anderer gleichartiger Fahrzeuge am gleichen Ort (um z.B. Streckensperrungen/Stau/Unfälle etc. zu erkennen)
- spezielle Tage, z.B. Zeitumstellung, Fahrplanwechsel gesondert berücksichtigen!

### Zusätzliche Daten, die intern berechnet werden können:
- Wochentag (aus Datum)
- Jahreszeit (aus Datum)

## Ablauf der Berechnung

- Einlesen der Eingabeparameter
- Fahrplandaten anfragen
- Zeitintervall ermitteln (Heuristik nach Verkehrsmittel)
- Gewichtungsfaktoren einlesen
- Echtzeit-Prognose anfragen
- Zeitliche Nähe der Echtzeit-Prognose in Gewichtung einrechnen
- für alle in der Gewichtung ausgewählten Einflüsse:
    - Daten anfragen
    - Wahrscheinlichkeitsverteilung für diesen Einfluss berechnen
    - mit Gewichtungsfaktor verrechnen
- alle Einflüsse zusammenrechnen zu einer Gesamtverteilung
- (optional zum debuggen/testen: einzelne Einflüsse und Gewichtungsfaktoren ausgeben.)
- Gesamtverteilung ausgeben