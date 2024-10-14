# Weserdatenbank - Softwarekonzept 

**Autoren Weserdatenbank Gruppe 3**: Tim Röckemann, Sascha Hahn, Jan-Ole Timo Löffler, Marc-Justin Leenders 

## Überblick

- Die Weserdatenbank soll zur Qualitätsüberwachung der Weser dienen zum Schutz des ökosystems, um Schadstoffe frühzeitig zu erkennen.
- Konzeptionelles Analyseklassendiagramm (logische Darstellung der Konzepte der Anwendungsdomäne)


## Funktionale Anforderungen

**Akteure** 

| **Akteur** | **Definition** |
| :------ | :----- |
| Admin | Der Administrator umfasst alle Berechtigungen und die Einstellung der Zugriffsberechtigungen |
| Benutzer | Angemeldeter Benutzer mit grundlegenden Berechtigungen. Kann Messstationen hinzufügen oder löschen |
| Zuschauer | Angemeldeter Benutzer mit wenigen Berechtigung alleinig zum anschauen der Informationen |


![](media/use-cases.png)

## Anforderungen im Detail

- Strukturierung der User Stories in funktionale Gruppen
- Sicherheit: Misuse-Stories formulieren

**User Stories**

| **Name**| **In meiner Rolle als**...|   ...**möchte ich**...   | ..., **so dass**... | **Erfüllt, wenn**... | **Priorität**   |
|:-----|:----------:|:-------------------|:-------------|:---------|:----------------|
| Chlorid und Ionen |Benutzer| Daten zu Chloridwerten und weiteren Ionen abrufen | Ich diese auf einer Webseite in einer bestimmten Darstellung sehen kann | Die Messwerte angezeigt werden | Muss |
| Hydrologische Daten | Benutzer | Möchte ich Daten wie Wasserstand und Fließgeschwindigkeit abrufen kann  | Ich diese Informationen angezeigt bekomme zum analysieren | Die Daten angezeigt werden | Muss |
| Kenngrößen | Benutzer | Kenngrößen wie Temperatur und PH-Werte überwachen | um eventuelle Umweltprobleme frühzeitig zu erkennen | Die Messwerte angezeigt werden | Muss |
| Metalle | Benutzer | Messdaten zu Metallen wie Blei oder Quecksilber abrufen können | um mögliche Verschmutzungen zu analysieren | Die Messwerte angezeigt werden | Muss |
| Nährstoffe | Benutzer | Daten zu Nährstoffen wie Stickstoff oder Phosphor abrufen | um den Einfluss auf das Ökosystem zu bewerten | Die Messwerte angezeigt werden | Muss |
| Summenparameter | Benutzer | Daten wie chemischen und biologischen Sauerstoffbedarf abrufen | um die organische Verschmutzung des Flusses zu analysieren | Die Messwerte angezeigt werden | Muss |
| Rollenvergabe | Admin | Benutzern eine Rolle zuweisen können | um diese in in ihren Berechtigungen ein zu schränken | Daten angezeigt werden | Muss |
| Messstation erstellen | Benutzern | eine neue Messstation hinzufügen können | man diese verwenden kann | Eine neue Messstation erstellt wurde | Muss |
| Messstation entfernen | Benutzern | eine Messsation aus den bestehenden löschen | diese nicht mehr zur Verfügung steht | Die Messstation nicht mehr vorhanden ist | Muss |
| Importieren | Benutzern | Eigene Messwerte zur Weserdatenbank importiere | diese Informationen hinzugefügt werden | Die Messwerte in der Datenbank liegen und auf der Seite dargestellt werden | Muss |
| Exportieren | Benutzern | Messwerte als eine Datei ausgeben lasen kann | Eine Datei mit den Informatioen erhalte | Die richtigen Information als Datei ausgegeben werden | Muss |
| Suche | Benutzern | Nach Stationen und den Messwerten nach verschiedenen Kritieren suchen können | um nach speziellen Informatioen zu schauen | Erfolgreich die Informationen mit den richtigen Filtern ausgegeben werden | Muss |

## Graphische Benutzerschnittstelle

- Screens mit Überschrift kennzeichnen, die im Inhaltsverzeichnis zu sehen ist
- Unter den Screens darstellen (bzw. verlinken), welche User Stories mit dem Screen abgehandelt werden
- Modellierung der Navigation zwischen den Screens der GUI-Mockups als Zustandsdiagramm
- Mockups für unterschiedliche Akteure

![]()


## Datenmodell 

**ERD**
![]()

## Abläufe

- Aktivitätsdiagramm für den Ablauf sämtlicher Use Cases
- Aktivitätsdiagramme für relevante Use Cases
- Aktivitätsdiagramm mit Swimlanes sind in der Regel hilfreich 
  für die Darstellung der Interaktion von Akteuren der Use Cases / User Stories
- Abläufe der Kommunikation von Rechnerknoten (z.B. Client/Server)
  in einem Sequenz- oder Aktivitätsdiagramm darstellen
- Modellieren Sie des weiteren die Diagramme, die für das (eigene) Verständnis des
  Softwaresystems hilfreich sind. 


## Schnittstellen

- **GET** ("/chlroid") Gibt alle Chloride und weitere Ionen wieder.
- **GET** ("/hdyrodaten") Gibt alle hydrologische Daten wieder.
- **GET** ("/kenngroeßen") Gibt die kontinuierlichen Kenngrößen wieder.
- **GET** ("/metalle") Gibt alle Metalle wieder.
- **GET** ("/naehrstoffe") Gibt alle Nährstoffe wieder.
- **GET** ("/schadstoffe") Gibt alle Schadstoffe wieder.
- **GET** ("/summenparameter") Gibt alle Summenparameter wieder.
- **POST** ("/...") Erstellt ...
- **PUT** ("/...") Updatet ...
- **DELETE** ("/...") Löscht ...



## Technische Umsetzung


### Softwarearchitektur

- Darstellung von Softwarebausteinen (Module, Schichten, Komponenten)

Hier stellen Sie die Verteilung der Softwarebausteine auf die Rechnerknoten dar. Das ist die Softwarearchitektur. Zum Beispiel Javascript-Software auf dem Client und Java-Software auf dem Server. In der Regel wird die Software dabei sowohl auf dem Client als auch auf dem Server in Schichten dargestellt.

* Server
  * Web-Schicht
  * Logik-Schicht
  * Persistenz-Schicht

* Client
  * View-Schicht
  * Logik-Schicht
  * Kommunikation-Schicht

Die Abhängigkeit ist bei diesen Schichten immer unidirektional von "oben" nach "unten". Die Softwarearchitektur aus Kapitel "Softwarearchitektur" ist demnach detaillierter als die Systemübersicht aus dem Kapitel "Systemübersicht". Die Schichten können entweder als Ganzes als ein Softwarebaustein angesehen werden. In der Regel werden die Schichten aber noch weiter detailliert und in Softwarebausteine aufgeteilt. 

![]()

### Fehlerbehandlung 

* Technische Fehler
  * Fehler 404 Not Found: ...
  * Fehler 422 Unprocessable Entity: ...
  * Fehler 500 Internal Server Error: Der Server hat einen Fehler beim Verarbeiten der Anfrage
  * SQL-Error: Ein Fehler im Umgang mit der Datenbank ist aufgetreten.
  * Timeout Error: Zeitüberschreibung

### Validierung

| **Fall** | **Beschreibung** | **Testschritt** | **Ergebnis** | 
| :------ | :----- | :----- | :----- | 
| Bauen | Das Projekt muss erfolgreich gebaut und deployt werden | Das Projekt wird gestartet | Das starten wird erfolgreich ausgeführt ohne auftretenden Fehler |
| Funktionalität | Alle Routen sowie die Middleware funktionieren | Alle Routen und somit auch die Middleware werden getestet | Erfolgreich oder durchgefallen |

Es muss grundsätzlich bevor jeder Route die Authentifizierung stattfinden um somit zu testen, ob die Berechtigung besteht um die Funktion auszuführen. Danach wird die Funktionalität der Route getestet in der man guckt, ob die Request mit den Userinputs auf richtigkeit validiert werden und somit erfolgreich in die Datenbank eingetragen werden können. Wenn alle diese Punkte erfolgreich abgeschlossen werden, ist der Test erfolgreich.

### Verwendete Technologien

- Verwendete Technologien (Programmiersprachen, Frameworks, etc.)

* Frontend: React.js Bootstrap und oder Material UI
* Backend: TypeScript
* Datenbank: PostgreSQL

* Wichtige Libs: Chart.js, MUI, React-leaflet, UI5-Webcomponents.
