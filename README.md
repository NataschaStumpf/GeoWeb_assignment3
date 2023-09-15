[![Work in Repl.it](https://classroom.github.com/assets/work-in-replit-14baed9a392b3a25080506f3b7b6d57f295ec2978f6f33ec97e36a161684cbe9.svg)](https://classroom.github.com/online_ide?assignment_repo_id=3937917&assignment_repo_type=AssignmentRepo)

# Übungsblatt 3

# Erstellung einer WebGIS Anwendung

In diesem Übungsblatt soll der gesamte Prozess einer WebGIS Anwendung durchgeführt werden. Dies umfasst Datenbeschaffung, Datenaufbereitung, Datenspeicherung, Datenbereitstellung, Datenvisualisierung und Datenabfrage über OGC-WMS GetFeatureInfo.


1) Datenbeschaffung (2 Punkte)**

Zur Durchführung der Aufgabe benötigen Sie Geometriedaten und Sachdaten verschiedener Bundesinstitutionen.

a) Laden Sie den Bundesländer-Datensatz für Geometrien von [hier](https://opendata-esri-de.opendata.arcgis.com/datasets/esri-de-content::bundesl%C3%A4ndergrenzen-2018) herunter.

b) Laden Sie den Ihnen zugeordneten statistischen Sachdatensatz als CSV-Datei herunter. Tragen Sie den gewählten Datensatz in Moodle ein. Hier geht es zu den Daten des Statistischen Bundesamtes DESTATIS: [DESTATIS Daten](https://www-genesis.destatis.de/genesis/online)

c) Falls Sie Ihre Werte nicht auf die Flächen sondern auf Bevölkerungszahlen beziehen möchten, laden Sie folgende Datei aus Moodle herunter, um Sie später mit den Bundesländern zu verknüpfen: `population_2015_12_31.csv`


2) Datenaufbereitung mit QGIS (5 Punkte)**

a) Um den statistischen Datensatz nutzen zu können, muss die Struktur der CSV Datei im Texteditor vereinheitlicht werden (1 Zeile pro Bundesland).

b) Importieren Sie die bereinigte Statistik-Tabelle, die Bundesländer und gegebenenfalls die Bevölkerungszahlen aus 1c) in QGIS.

c) Verknüpfen Sie die Geometrien mit den Sachdaten (Layer->Eigenschaften->Verknüpfungen) auf Basis der Bundeslandbezeichnung in QGIS und importieren Sie das Ergebnis in Ihre PostgreSQL/PostGIS Datenbank (UNI VPN!).

d) Erzeugen Sie mit Hilfe von QGIS einen geeigneten kartographischen Stil für den Layer in der Datenbank und exportieren Sie diesen als SLD-Datei. Setzen Sie die Werte Ihrer Statistik in Beziehung zur Fläche bzw. der Bevölkerungszahl des jeweiligen Bundeslandes.


3) Datenbereitstellung mit GeoServer (5 Punkte)**

Geoserver URL (UNI VPN): [GeoServer](http://osmatrix.geog.uni-heidelberg.de:8080/geoserver-2.18/web)

a) Legen Sie im GeoServer einen neuen SLD Style an, der im nächsten Schritt mit Ihrem Layer verknüpft werden soll.

b) Legen Sie nun einen neuen Layer mit Ihren Daten aus der Datenbank an. Achten Sie darauf, Ihren eigenen Workspace zu verwenden, wenn Sie den Datenspeicher und den Layer anlegen. Testen Sie Ihren Layer in der Layervorschau.


4) Datenvisualisierung und Abfrage mit OpenLayers (8 Punkte)**

a) Erstellen Sie eine HTML-Datei mit einer OpenLayers Anwendung und binden Sie Ihren GeoServer Layer als WMS-Layer ein.

b) Erstellen Sie ein interaktives Abfragewerkzeug, welches durch einen Klick auf die Karte die Attribute des jeweiligen Bundeslandes anzeigt. Verwenden Sie hierfür die WMSGetFeatureInfo Abfrage.
