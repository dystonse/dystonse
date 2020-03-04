# Potentielle Komponenten

## Erste Gedanken dazu:
 * Anfragen von Daten verschiedenen Formaten
 * Datenbank, die alle drei Formate von Echtzeitdaten unterstützt
 * evtl. überflüssig: Konvertieren aller Daten in ein gemeinsames Format
 * evtl. überflüssig: Datenbank für unser primäres Format
 * Berechnen von Prognosen als Wahrscheinlichkeitsverteilung
 * Datenbank für Prognosen als Wahrscheinlichkeitsverteilung
 * selbst aktualisierende OSM-Datenbank
 * Shape-Generator mit Pfaedle
 * selbst aktualisierende Fahrplan-Datenbank
 * Suchserver
 * Webserver
 * Statistische Auswertung der Vergangenheit

Datenbanken können dabei als eigenständiger Host vorliegen und/oder gespiegelt auf dem Host, der letztlich mit der DB arbeitet, wenn die Latenzen oder der Durchsatz zwischen den Hosts sonst zu groß wäre

## Grafik
![Kiku](./Dystonse&#32;Komponenten.png)