___

# Compocloud Biofilter
___


___

## Biofilter-Widget
___

Ist die Anlage mit einem Biofilter und einem Biofiltergebläse ausgestattet, wird nach den Mieten-Widgets das Widget für den Biofilter eingeblendet.
Durch einen Klick auf das Biofilter-Widget im helleren Bereich wird der Biofilter-Bereich geöffnet.

![Biofilter](/assets/images/Docs/Compocloud/Biofilter.png)

Das Widget zeigt den aktuellen Status des Biofilters mit folgenden Werten:

- **A**: Die aktuelle Temperatur im Biofilter

- **B**: Der aktuelle Druck vor dem Gebläse (zwischen Mieten und Gebläse)

- **C**: Die Drehzahlvorgabe an das Biofiltergebläse. Im Normalfall entspricht 100% 50Hz.

- **D**: Der aktuelle Druck nach dem Gebläse (vor dem Biofilter)

- **E**: Status des Gebläses. Bei Betrieb des Gebläses rotiert der Flügel, bei einer Störung wird der Hintergrund rot dargestellt. Bei einer Störung wird zusätzlich der Alarm unter der Kopfzeile angezeigt.

- **F**: Modus Ein: Ist dieser Modus aktiv, das Zeichen ist hervorgehoben wie H, läuft das Biofiltergebläse auf Dauerbetrieb bis der Benutzer den Modus ändert oder eine Störung auftritt. Ist dieser Modus aktiv, wird zusätzlich die Sollwertvorgabe für den Ein-Modus (I) dargestellt.

- **G**: Modus Aus: In diesem Modus wird das Biofiltergebläse gestoppt.

- **H**: Modus Automatik: In diesem Modus wird das Biofiltergebläse gestartet und die Drehzahlvorgabe erfolgt über einen Regler. Dieser versucht den Druck vor dem Gebläse (B) auf einen eingestellten Wert durch anpassen der Drehzahlvorgabe zur regeln. Im Kapitel Biofilter-Automatik ab Seite 20 wird die Funktionsweise der Automatik detaillierter beschrieben.

- **I**: Drehzahlvorgabe Modus Ein: Wird nur eingeblendet, wenn sich das Biofiltergebläse im Modus ‚Ein‘ befindet. Durch Drücken auf das Symbol wird ein Dialog für die Änderung des Sollwertes eingeblendet. Der Wert kann direkt eingegeben oder durch das Verschieben des Reglers angepasst werden. Durch Drücken auf `Speichern` wird der Wert übernommen. Durch Drücken auf `Abbrechen` wird der Dialog ohne Änderung geschlossen.

Das Ändern des Modus (F, G, H) und der Drehzahlvorgabe (I) ist nur für ‚ Operator‘ oder Benutzer mit höher Berechtigung möglich.

___

### Einstellungen
___

Die Einstellungen eines Biofilters können über den Menüpunkt `Parameter`, ein Unterelement des Biofilters, geöffnet werden. Änderungen können nur von Benutzer in einer Benutzerrolle gleich oder größer `Operator` (Bedienpersonal) durchgeführt werden. Nach dem Ändern eines Wertes wird dieser durch Drücken von `Speichern` an die Steuerung übertragen.

- **Solldruck vor Gebläse (A)**: Solldruck welcher in den Kompostiergebäuden durch das Gebläse gehalten werden soll.

- **Biofilter Max. Temperatur (B)**: Maximaltemperatur im Biofilter. Details siehe Kapitel `Ablauf`.


- **Biofilter Temperatur Hysterese (C)**: Hysterese für das Freischalten der Gebläse nachdem das Maximum überschritten wurde. Details siehe Kapitel `Ablauf`.

- **Intervallbreite für Abschaltautomatik (D)**:


![Setting Biofilter Automatic](/assets/images/Docs/Compocloud/SettingBiofilterAutomatic.png)

___

### Funktionsbeschreibung
___

Der Biofilter besteht aus:

- Biofiltergebläse (frequenzgeregelt) - M<small>BLOWER</small>
- Temperatursensor im Biofilter - T<small>BIO</small>
- Drucksensor Saugseite Gebläse (Seite Boxen) - P<small>IN</small>
- Drucksensor Druckseite Gebläse (Seite Biofilter) - P<small>OUT</small>

##### Betriebsmodi

Der Benutzer kann am Biofilter-Widget zwischen 3 Modi wählen:

- **ON**: Dauerbetrieb: Das Biofiltergebläse ist eingeschalten und die Drehzahlvorgabe erfolgt durch den Benutzer
- **OFF**: Biofiltergebläse ist ausgeschalten
- **AUTO**: Automatikbetrieb: Das Biofiltergebläse ist eingeschalten und die Drehzahlvorgabe erfolgt durch einen Regler, welcher einen eingestellten Solldruck zu halten versucht.

Details über die verschiedenen Modis des Biofiltergebläses finden sie im Kapitel `Biofilter-Widget`.


##### Ablauf
Wenn sich das Biofiltergebläse im Automatik-Modus befindet, wird das Gebläse gestartet und über einen Regler wird die Drehzahl so angepasst, dass der Druck vor dem Gebläse (Ist-Wert) dem eingestellten Sollwert A näher kommt. Diese Regelung dient dazu, in den Kompostierhallen einen Unterdruck zu halten. Sollte ein Tor geöffnet werden, so versucht er, dem höheren Druckausgleich entgegenzuarbeiten. Gleichzeitig wird eine Warnung angezeigt. Zeigt der Drucksensor einen Fehler an (Wert liegt nicht zwischen 4 und 20 mA) wird das Abluftgebläse mit der Minimal-Drehzahl betrieben.
Sollte die Temperatur im Biofilter die Maximaltemperatur B überschritten werden, wird eine Warnung ‚Biofilterschutz aktiv‘ ausgegeben. Diese Warnung bleibt gesetzt bis die Temperatur im Biofilter wieder unter die Maximaltemperatur B minus einer Hysterese C fällt. Ist diese Warnung aktiv, werden die Mieten- und Biofiltergebläse gestoppt.
