# aWATTar-smart-Victron-ESS-
Dieser Node-Red-Flow optimiert die Ladung bei günstigen Strompreisen in Kombination mit dem Energieanbieter aWATTar.

Vorab: Dies ist mein erstes Node-Red-Projekt, also habt bitte Nachsicht. Bei einigen dingen hat mir auch ChatGPT sehr geholfen! Schreibt mir gerne eure Verbesserungsvorschläge oder auch Funktionen, die ihr für nützlich empfindet.

Ablauf:
- Der Flow holt sich von der aWATTar-API um 13:00 Uhr die aktuellen Preise. 30 Minuten später erneut, da manchmal die Daten um 13:00 Uhr noch nicht verfügbar sind.
- Anschließend werden die günstigsten Stunden gefiltert und gespeichert.
- In der nächsten Zeile wird jede Stunde überprüft, ob sich der Flow in einer der günstigsten Stunden befindet und der Preis unter der Grenze liegt.
- Dies wird dann als 0 oder 1 weitergegeben, und einerseits wird der EV-Charger gestartet/gestoppt, und andererseits wird der Speicher geladen.
- Die Funktion "Nachtladung" prüft in der Nacht, ob die Batterie eine günstige Ladung vertragen könnte.

Benutzerparameter zum selbsteinstellen:
<img width="793" alt="image" src="https://github.com/Scooolt/aWATTar-smart-Victron-ESS-/assets/154541138/7e5882f6-5c1b-4b70-90db-c79cab47a273">

Flowübersicht (noch mit einigen debug nodes)
<img width="1096" alt="image" src="https://github.com/Scooolt/aWATTar-smart-Victron-ESS-/assets/154541138/a3867fcc-bc81-48da-a22f-25ad02d4ca11">

