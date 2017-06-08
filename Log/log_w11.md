# Logboek Week #11  (24/04/17 - 28/04/17)
### Maandag
* Updaten Python libraries en packages voor terminal beheer op Raspberry Pi 3B.
* Updaten van Docker op laptop:
	* **probleem**: Docker werkt alleen op Windows 10 Pro & Enterprise
	* **oplossing**: installeren Docker "legacy" toolbox
	* installeren van Docker toolbox (success)
	*  verifiëren van de installatie
	*  testen van local container/image op laptop
	*  aanvragen credentials en connection informatie om in Digipolis Docker omgeving te kunnen werken.
*   Uitfrezen Raspberry cases voor kabel management.
*   Installeren van Digipolis bitbucket webservice API template.

### Dinsdag
  * Update schema prototype Fritzzing.
  * Toevoegen van LDR in het schema.
  * Updaten 'Bill of materials'.
  * Wekelijkse synchronisatie:
	  * status van het prototype
	  * 'Bill of materials'
	  * 2 mei titel thesis definitief
	  * status van Docker Image
		  * Docker image lokaal ontwikkelen
		  * webserver API in ASP.NET Core ontwikkelen
		  * afleveren van Image
		  * implementeren doet Digipolis zelf.
  * Aanpassen van sensor Python code aan het nieuwe Fritzing schema. 

### Woensdag
* Testen Pir-STD met Led:
	* probleem: geen reactie
	* oplossing: Syntax fout Python code converteren naar Python 3
	* Raspberry Pi met Pir en Led werkt.
* Testen van Raspberry Pi linken naar NSX MQTT Broker:
	* probleem: Syntax fout in formaat Username "naam.achternaam"
	* oplossing: nieuwe username formaat aanvragen bij NSX.

### Donderdag
* Opstellen van eventhandler project in Docker.
* Configureren van MQTT Publisher op Raspberry Pi:
	* voorzien van password encryptie bij MQTT login
	* topic structuur van MQTT message
	* username (wachten voor aanpassing bij NSX)
	* aanpassen van variabelen die moeten worden gepubliceerd. 
* Testen van data verzenden naar NSX.
* Opzoeken: automatisch opstarten van Python script on boot van Raspberry Pi. 

### Vrijdag
* Werken aan scriptie en voortgansverslag.