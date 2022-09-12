___

# Compocloud Übersicht
___

Dieses Dokument dient als Benutzerhandbuch für die Bedienung einer COMPOcloud-Anlage über die mandy-Oberfläche. 
Um mehr über das Starten und Auswählen einer Anlage zu lesen, lesen sie bitte:

[Mandy - Setup und Einstieg](/#/help?folder=mandy&page=setup)

Wird auf der `Auswahl`-Seite auf eine COMPOcloud-Anlage gedrückt, so wird die Übersicht zu dieser Anlage geöffnet.
Auf der Eingangsseite werden oben eine Kopfzeile für das Navigieren und darunter die Mieten einer Anlage dargestellt. Sollte die Anlage mit einem Biofilter ausgestattet sein, so wird dieser nach den Mieten eingeblendet.


Falls sie mehr über eine Miete in Erfahrung bringen wollen, lesen sie bitte:

[Mandy - Miete](/#/help?folder=compoCloud&page=windrow)

Um mehr über den Biofilter zu erfahren, lesen sie bitte:

[Mandy - Biofilter](/#/help?folder=compoCloud&page=biofilter)



___

## Kopfzeile
___

In der Übersicht kann über eine Kopfleiste zwischen verschiedenen Ansichten gewechselt werden. 
Die aktuelle Ansicht wird farblich (dunkelrot) hervorgehoben.

![Compocloud Overview](/assets/images/Docs/Compocloud/Uebersicht.png)

Grundsätzlich stehen folgende Ansichten (Seiten) zur Verfügung, abhängig der Rolle des aktuell angemeldeten Benutzers:

- **ÜBERSICHT**: Zeigt den Status aller Mieten an. Diese Seite ist für jeden Benutzer zugänglich.
- **LOGS & EXPORT**: Auf dieser Seite können die aufgezeichneten Messwerte aller Mieten in einem Chart ausgegeben werden. 
  Diese Seite ist für alle Benutzer, ausgenommen  Besucher, zugänglich.
- **EINSTELLUNGEN**: Hier können allgemeine Einstellungen vorgenommen werden. Diese Seite ist nur für Benutzer mit Rolle Operator, Manager und Administrator zugänglich.
- **SYSTEM** (ADMIN): Hier können Systembefehle an den IoT-Client gesendet werden. Benutzer der Gruppe Administrator können diese Seite öffnen.
- **QUITTIEREN**: Bestätigung von Alarmen. Wird eingeblendet wenn ein Alarm bzw. Fehler aktiv ist.
- **SIGNALSTÄRKE und NETZBETREIBER**: Rechts wird die Signalstärke des Empfangs des 3G/4G-Modem und der Name des Netzbetreibers dargestellt. 
  Der Wert der Signalstärke sollte größer als -82dBm sein.
- **AUSSENTEMPERATUR**: Ist ein Bewässerung vorhanden, wird die Außentemperatur neben den Netzinformationen dargestellt.


Zusätzlich kann über das seitliche Menü zu den einzelnen Ansichten navigiert werden.
___

## Anzeige aktiver Alarme
___

Alle derzeit aktiven Fehlermeldungen, die sich nicht auf einen Teilbereich wie eine Miete oder einen Biofilter beziehen, werden in der Übersicht der Mieten unterhalb der Kopfleiste angezeigt. Die Beschreibung der Meldung wird angezeigt, gefolgt vom Zeitstempel der ausgelösten Meldung.

![Error Message](/assets/images/Docs/Compocloud/COMPOcloud_Overview-Alarms_DE.PNG)

Durch Drücken auf den Button `QUITTIEREN` in der Kopfzeile in der Übersicht oder durch Drücken auf den Reset-Taster am Schaltschrank können Alarm bestätigt und rückgesetzt werden.

___

## Logs&Export
___

Auf dieser Seite können die gemessen Temperaturen aller Mieten für einen durch den Benutzer definierten Zeitraum ausgegeben und exportiert werden. Der Benutzer kann ein Von- und Bis-Datum selbst definieren. Durch Drücken auf TAG, WOCHE, MONAT wird die gewünschte Dauer mit dem aktuellen Datum als ‚Bis‘-Datum gesetzt.
Nach Auswahl des Zeitraumes können die Daten durch Drücken auf ‚LOGS & EXPORT‘ in der Vorschau dargestellt werden. Mit ‚HERUNTERLADEN‘ können diese am Endgerät abgespeichert werden.

___

## Einstellungen
___

Auf diese Seite könne allgemeine Einstellungen durchgeführt werden. Die Übernahme eines Wertes erfolgt nach Drücken von SPEICHERN.

- **Übertragungsintervall**: Zeitintervall für das Lesen und Übertragen von Daten-Variablen and die Mandy-Plattform. Wird nur bei älteren Anlagen mit IoT-Client v1 eingeblendet.
- **Bewässerung - Entwässerungszeit**: Die Dauer der Entwässerung (Entleerung) nach einem Bewässerungszyklus. Die Entwässerung wird nur ausgeführt, wenn die Außentemperatur unter 5°C liegt um Frostschäden am System zu verhindern. Wird nur eingeblendet wenn eine Bewässerung vorhanden ist.
- **Bewässerung - Anzahl der Ventile**: Maximale Anzahl der Bewässerungsventile Mieten, welche zeitgleich geöffnet werden können. Abhängig vom zur Verfügung stehenden Wasserdruck kann es bei zu vielen offenen Ventilen zu einem sehr geringen Druck im System kommen und weiter entfernte Mieten werden nicht ordentlich bewässert. Stellen sie diesen Wert so ein, dass bei dieser Anzahl genügend Wasserdruck auch in der entferntesten Miete vorhanden ist. Wird nur eingeblendet wenn eine Bewässerung vorhanden ist.

___

## Miete
___

In der Übersicht wird für jede Miete ein Mieten-Widget eingefügt. Wird in der Übersicht auf eine gewünschte Miete gedrückt, wird die Übersicht einer Miete geöffnet. Für das Öffnen nicht in die Befehlszeile (dunkler Bereich) drücken. Die Befehlzeile befindet sich im unteren Viertel des Widgets. 
Auch kann durch das Drücken auf das Untermenü ‚Miete‘ einer Miete diese Ansicht geöffnet werden. Es wird in der Übersicht einer Miete das Mieten-Widget dargestellt. Weitere Untermenüs sind CHART, MELDUNGEN und PARAMETER.

___

## Biofilter
___

Ist die Anlage mit einem Biofilter ausgestattet, wird ein zusätzliches Widget für diesen angezeigt. 
Wird in der Übersicht auf einen gewünschten Biofilter gedrückt, wird die Übersicht des Biofilters geöffnet. Auch kann durch das Drücken auf das Untermenü ‚Biofilter‘ einer Biofilters diese Ansicht geöffnet werden. Es wird in der Übersicht eines Biofilters das Biofilter-Widget dargestellt. Weitere Untermenüs sind CHART, MELDUNGEN und PARAMETER.
