# Logboek Week #9  (27/03/17 - 31/03/17)
### Maandag
* Tussentijdse presentatie bachelorproef
### Dinsdag
* Vastleggen van de software architectuur voor het project  
* Wekelijkse sycnhronisatie gesprek
 * Review tussentijdse presentatie
     * Waarom project niet op Lora?
     * Waarom project niet op WiFi?
     * Mogelijkheid om Raspberry Pi Zero W te bestellen voor het project? 
     * Setup Docker
     * Bijhouden van selectieve sensor data
     * Resolutie van het verzenden van data/tijd
     * Topic 'DA2/V5/Caracara"
     * MQTT Topic: Sensornaam
	     * QoS 0: Data published "at most once", ontvanger kan het eenmalig ontvangen (risico paketje verlies)
		 *	**Qos 1: Data published "at least once", Data blijft bijgehouden opgeslagen, tot subscriber bevestiging stuurt (risico paketjes duplicaat)**
		 *	QoS 2: Data published "exactly once", Data blijft opgeslagen tot er een ontvangtsbevestiging is ontvangen + controle op duplicaten
	* Package ID
	* Device ID
	* PIR Activiteit / 2min
	* Temperatuur
	* Vochtigheidsgraad
	* Date/timestamp
 * Review use-case van het project vastlegggen
 * Donderdag 17:15 Infomoment Ferranti (1 x wisselen met vrijdag)
 * Afwachten resultaat bespreking met NSX over het hosten van de MQTT Broker en Sensor data storage in local Amazon S3 DataLake
### Woensdag
* Opzoeken Pythonscript voor PIR
* Opzoeken Pythonscript voor MQTT
* Aanvragen van MQTT Broker gegevens bij NSX 
### Donderdag
* Werken aan scriptie
* Vastleggen van software architectuur
### Vrijdag
* Schrijven van Raspberry Pi Pythonscript voor PIR Sensor en MQTT Publisher
* Opstellen van een MQTT testomgeving