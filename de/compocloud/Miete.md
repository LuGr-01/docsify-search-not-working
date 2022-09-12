___

# Compocloud Miete
___



___

## Mieten-Widget
___

In einem Widget werden alle Messwerte und Statusinformation zu einer Miete dargestellt.

![Mieten-Widget](/assets/images/Docs/Compocloud/COMPOcloud_Windrow-Widget_DE.png)

Folgende Werte werden hier ausgegeben:

- **A**: Name der Miete.

- **B**: Die Steuerungstemperatur. Dieser Wert berechnet sich aus den gemessenen Temperaturwerten und der eingestellten Berechnungsmethode (siehe D)

- **C**: Gebläse-Status: Rotiert wenn das Gebläse in Betrieb ist. Bei einer Störung des Gebläses wird dieser rot hinterlegt.

- **D**: Die eingestellte Methode für die Berechnung der Steuerungstemperatur. Mögliche Werte sind:

    - **Mittelwert**: Berechnet den arithmetischen Mittelwert aus allen Temperaturen
    - **Minimum**: Die niedrigste gemessene Temperatur
    - **Maximum**: Die höchste gemessene Temperatur
    - **Temperatur 1 – Temperatur 5**: Der gemessene Wert eines bestimmten Temperatursensors wird verwendet.

- **E**: Temperatur 3: Gemessene Temperatur von Sensor 3 (bei TML-3 der oberste Sensor)

- **F**: Temperatur 2: Gemessene Temperatur von Sensor 2

- **G**: Temperatur 1: Gemessene Temperatur von Sensor 1. Dieser Sensor befindet sich in der Spitze der Lanze.

- **H**: Signalqualität: Verlust des Signals von der Lanze bis zum TML-Empfänger. Je höher der Wert (Achtung! Negative Zahl!), umso besser das empfangene Signal. Folgende Grenzwerte:

|     von            	|     bis          	|     Qualität                   	|
|--------------------	|------------------	|--------------------------------	|
|     <= -100dBm     	|     -90dBm       	|     Sehr schlechter Empfang    	|
|     -90dBm         	|     -80dBm       	|     Schlechter Empfang         	|
|     -80dBm         	|     -70dBm       	|     Mittelmäßiger Empfang      	|
|     -70dBm         	|     -60dBm       	|     Gut                        	|
|     -60dBm         	|     >= -50dBm    	|     Sehr Gut                   	|

- **I**: Batteriespannung

|     von       	     |     bis          	|     Kapazität      	          |
|--------------------	|------------------	|--------------------------------	|
|     2900mV    	     |     3100mV       	|     Leer           	          |
|     3100mV    	     |     3300mV       	|     Fast   leer                  |
|     3300mV    	     |     3500mV       	|     Fast   voll                  |
|     3500mV    	     |     3600mV       	|     Voll           	          |
|     -60dBm    	     |     >= -50dBm    	|     Sehr Gut       	          |

- **J**: Zeitstempel, wann zuletzt ein Datenpunkt vom Gerät (IoT-Gateway) empfangen wurde.

- **K**: Bewässerungsmengen. Links befindet sich die aktuelle Tagesmenge, rechts die Solltagesmenge. Wird nur dargestellt wenn diese Miete mit einem Bewässerungsventil ausgestattet ist.

- **L**: Name der aktuellen Charge. Ist kein Batch zugewiesen, werden anstelle des Namens drei Punkte (‚…‘) dargestellt.

- **M**: Bearbeiten der Charge für diese Miete. Wird auf dieses Element gedrückt, erscheint der Dialog für das Bearbeiten der Charge.
___

### Charge bearbeiten
___

Wird auf das Bearbeiten-Symbol (M) geklickt, öffnet sich ein Dialog.
Der Benutzer kann hier die nächste Tätigkeit wählen. Mögliche Aktionen sind:

- **Material hinzufügen**: Dieser Button wird nur angezeigt, wenn keine Charge auf dieser Miete vorhanden ist. Drücken sie auf diese Aktion, wird unterhalb ein Eingabefeld für den Name der neuen Charge eingefügt. Geben sie einen neuen, eindeutigen Namen für diese Charge ein und drücke sie auf `Material hinzufügen`. Nach dem Hinzufügen sollte der Name auf der Position `J` wiedergegeben werden.
- **Material umsetzen**: Dieser Button wird nur angezeigt, wenn eine Charge auf dieser Miete vorhanden ist. Drücke sie auf diesen Button, erscheint eine Auswahlliste von möglichen Zielmieten. Wählen sie eine Miete als Ziel für diese Charge und drücken sie auf `Material umsetzen`.
- **Material entfernen**: Entfernt das Material (die Charge) von einer Miete. Diese steht danach nicht mehr zur Verfügung. Drücken sie auf diese Aktion, werden sie gefragt, ob sie diese Charge sicher verwerfen wollen. Wenn ja, bestätigen sie mit `Ja` ansonst `Nein`.

___

### Mietengebläse
___

Im unteren Bereich werden die möglichen Betriebsmodis (A1-A4) des Mietengebläses dargestellt. Der aktive Modus wird hervorgehoben (siehe A4).

![Mietengebläsesteuerung](/assets/images/Docs/Compocloud/MietenSteuerung.png)

##### Dauerbetrieb (A1)
Gebläse wird durch den Benutzer durch Drücken und Bestätigung des nachfolgenden Dialogs gestartet. Es läuft solange bis dieses Gebläse durch den Benutzer durch die Anwahl eines anderen Modus oder durch eine Störung gestoppt wird.

##### Ausgeschalten (A2)
Das Gebläse wird gestoppt.

##### Intervall-Modus (A3)
Das Gebläse wird für eine eingestellte Zeit ein- bzw. ausgeschaltet. Nach Ablauf der Pausezeit (ausgeschalten), wird wieder mit der Betriebszeit (eingeschalten) begonnen.
Die Einstellung erfolgt über die Parameter-Seite dieser Miete.

##### Temperatur-Modus (A4)
Das Gebläse wird ähnlich dem Intervall-Modus betrieben. Jedoch werden die Betriebszeit und die Pausezeit aus der Steuerungstemperatur (B) über lineare Funktionen ermittelt.
Die Einstellung der Temperaturen und Zeiten erfolgt über die Parameter-Seite dieser Miete.

##### Modus Lokal (AM)
Ist das Mietengebläse mit einer lokalen Bedienstation (LBS) ausgestattet, so kann die Steuerung über diese LBS oder dem Steuerungssystem (SPS) erfolgen. Die LBS befindet sich meist auf der Vorderseite einer Schaltschranktür. Über eine 2-färbige LED wird der Status des Gebläses wiedergegeben. Rot bei einem Fehler (z.B. Motorschutz gefallen, Überhitzung Motor,...) und Grün bei Betrieb (Motorschütz angezogen).

Positionen Wahlschalter:
- **Lokal (Hand)**: Dauerbetrieb Gebläse. Auch möglich wenn das Steuerungsystem ausgeschalten ist.
- **Aus (Off)**: Stopp Gebläse.
- **Fern (Auto)**: Steuerung erfolgt über das Steuerungssystem. Eine Auswahl eines Betriebsmodi (A1-A2) i st möglich.

Befindet sich der Wahlschalter auf Position `Lokal`(Hand) oder `AUS`(Off), so ist eine Steuerung des Gebläses über das Steuerungssystem unterdrückt.

![Mietengebläse Lokale Steuerung](/assets/images/Docs/Compocloud/COMPOcloud_WindrowControlLocal.PNG)
___

### Bewässerung
___

Direkt unterhalb der Modusauswahl des Mietengebläses werden die möglichen Betriebsmodis (B2-B4) der Bewässerung dargestellt. Der aktive Modus wird hervorgehoben (siehe B3). Dieser Teil wird nur eingeblendet wenn eine Bewässerungsventil für diese Miete vorhanden ist.

![Mieten Irrigation Control](/assets/images/Docs/Compocloud/MietenSteuerungIrrigation.png)

##### Status Ventil (B1)

Zeigt ob das Bewässerungsventil geöffnet oder geschlossen (durchgestrichen) ist. Wird auch als Offen dargestellt, wenn nach einer Bewässerung die Entleerung für diese Miete aktiv ist.

##### Dauerbewässerung (B2)

Startet die Bewässerung für diese Miete, bis der Benutzer den Modus wechselt oder ein Fehler auftritt. Die Menge wird zur aktuellen Tagesmenge hinzugefügt. 
Wird die Bewässerung gestoppt und die Außentemperatur ist unter 5°C, wird dieser Zweig des Systems entleert. Die Dauer der Entleerung kann in den allgemeinen Einstellungen parametriert werden.

##### Ausgeschalten (B3)

Bewässerung ist für diese Miete deaktiviert.

##### Automatik (B4)

Der Benutzer kann in den Parametern für die Miete eine Zyklusmenge und eine Tagessollmenge einstellen. Basierend auf diesen Einstellungen werden die Anzahl der Zyklen und der nächste Startzeitpunkt (B6) berechnet. Ist die aktuelle Zeit gleich dem nächsten Startzeitpunkt, wird die Zyklusmenge (Tagessollmenge/Anzahl der Zyklen) eingebracht. Die aktuelle Tagesmenge wird nach Abschluss der Bewässerung aktualisiert und im Mietenwidget unter K und B5 dargestellt. 
Wird die Bewässerung gestoppt und die Außentemperatur ist unter 5°C, wird dieser Zweig des Systems entleert. Die Dauer der Entleerung kann in den allgemeinen Einstellungen parametriert werden.

___

### Mieten-Einstellungen
___

Auf dieser Seite können sie die Einstellung für diese Miete durchgeführt werden.

#### Intervalleinstellungen

Einstellungen für das Mietengebläse im Modus ‚ Intervall‘. Befindet sich das Gebläse in diesem Modus, wird es für die eingestellte ‚Laufzeit‘ eingeschalten und für die eingestellte ‚Pausenzeit‘ ausgeschalten.

![Setting Intervall](/assets/images/Docs/Compocloud/SettingIntervall.png)

#### Automatikeinstellungen

Einstellungen für das Mietengebläse im Modus ‚Temperatur‘. Mit Hilfe einer linearen Funktion wird die Laufzeit und Pausenzeit in Anhängigkeit zur Steuerungstemperatur der Miete ermittelt. Die linke Seite beschreibt die Mindestlaufzeit bzw. -pausenzeit bei einer gewünschten Temperatur. Die rechte Seite ist die Maximallaufzeit bzw. pausenzeit bei einer gewünschten Temperatur. Die Lauf- bzw. Pausenzeit werden durch diese Werte begrenzt.

![Setting Automatic](/assets/images/Docs/Compocloud/SettingAutomatic.png)

#### TML-Einstellungen

- **Seriennummer**: Seriennummer der Temperaturlanze welche dieser Miete zugeordnet werden soll. Bei TMLv4 mit WLAN sind nur die letzten acht stellen einzugeben.
- **Regelungstemperatur**: Auswahl welche Temperatur für die Berechnung der Lauf-Pausenzeiten des Mietengebläses im Modus ‚Temperatur‘ herangenommen werden soll. Details siehe Kapitel Mieten-Widget (D) Seite 11.

![Einstellungen TML](/assets/images/Docs/Compocloud/SettingTML.png)

#### Bewässerungseinstellungen

Wird nur angezeigt wenn diese Miete mit einem Bewässerungsventil ausgestattet ist.

- Tagesmenge: Menge welche jeden Tag bewässert werden soll. Ist diese Menge erreicht wird die Bewässerung gestoppt.
- Intervallmenge: Menge die jeden Bewässerungszyklus aufgebracht werden soll.

![Setting Irrigation](/assets/images/Docs/Compocloud/SettingIrrigation.png)
