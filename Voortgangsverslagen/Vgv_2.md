# Voortgangsverslag #2
# Titel onderwerp: IoT-Smart buildings: Het gebruik van vergaderzalen optimaliseren door inzet van sensors

## Promotors

* **Stagebegeleider**
  * Maarten Luyts - Maarten.Luyts@ap.be
* **Stagementor**
  * Greet Brosens - Greet.Brosens@Digipolis.be
  * Rudi De Geest - Rudi.deGeest@Digipolis.be
* **Stagegever** (Stage coördinator Digipolis)
  * **Stijn Matthe - Stijn.Matthe@Digipolis.be**
* **Stagecoördinators**
  * Maarten Luyts - Maarten.Luyts@ap.be
  * Marc Smets - Marc.Smets@ap.be

## Abstract
<!--Het abstract is een samenvatting van je totale bachelorproef, inclusief reeds gekende resultaten-->

Het IoT project van het automatisch vergaderzaalbeheer in Exchange server 2016 is stapsgewijs tot stand gekomen. Hiervoor is het project gestart met een goedkope technologie en een simpele autonomie zoals de Arduino Uno microcontroller en een Passive Infrared Sensor (PIR) om activiteit in een vergaderzaal te detecteren. Naarmate het project vorderde is het project geëvolueerd naar het gebruik van meer intelligente hardware zoals de Rasberry pi 3B om aan de projecteisen te voldoen. Bij de start van het project was ook nog niet duidelijk welke sensordata nuttig zou zijn om op lange termijn op te slaan. De resultaten voor de software zijn nog niet gekend. Dit zou het projectonderzoek moeten uitwijzen. Maar voor de Hardware staat vast dat een Raspberrry Pi 3B en PIR Sensor zal gebruikt worden om activiteit in een vergaderzaal te detecteren. 

## Technische omschrijving
<!--Technische omschrijving van de evolutie van het project tijdens de betrokken periode, met aanduiding van de reeds bekomen resultaten en een planning voor de verdere uitwerking, welke problemen zijn ondervonden en hun oplossingen:-->
<!--Minimum 3000 woorden-->

Het automatisch beheren van het vergaderzalenproject is stapsgewijs tot stand gekomen. Tijdens de ontwikkeling van het project zijn er veel technologieën aan bod gekomen. In eerste instantie lag de focus op het essentiële gebruik van de sensors en het aanspreken naar de Exchange server. De Arduino Uno Rev.3 en een Passive Infrared Sensor (PIR) is gebruikt om activiteit in een vergaderzaal te detecteren. De Arduino microcontroller geeft sensordata draadloos door aan een server die een PowerShell script host. Hiervoor maakt de Arduino controller gebruik van een zelfstandige ESP8266 Wifimodule. Het PowerShell script controleert op de Exchange server of de vergaderzaal gereserveerd is door de Exchange Web Service API (EWS) aan te spreken. Zo vergelijkt het script de datum/tijd van de reservatie met de ontvangen sensordata. Als het script de eerste 30 minuten van de vergadering of 20 minuten nadat de vergadering is begonnen geen activiteit detecteert in de vergaderzaal zal het script de reservering van de vergadering op de Exchange Server annuleren. Zo kan de vergaderzaal door iemand anders opnieuw geboekt worden. De events die het script onderneemt, zou worden bijgehouden in een PostgreSql databank. De databank verzamelt informatie over de bezetting en de redenen waarom de reservatie van de vergaderzaal is geannuleerd. Het eerste probleem dat zich voordeed bij het testen van het eerste prototype was de verbinding van de Arduino aan het WiFi netwerk van Digipolis. Deze gebruikt WPA2-Enterprise PEAP-MSSHAPv2 encryptie. Voor het project zijn er drie opstellingen getest. De eerste was een Arduino Uno met externe ESP8266 wifi module, de tweede een Arduino Uno met WizzFiShield en de derde een Arduino Featherwing HUZZAH. Tot op heden van dit project is de ondersteuning van Enterprise encryptie voor Arduino echter beperkt. Als oplossing voor dit probleem kan een Root Certificaat binair op de Arduino geplaatst worden. Maar dit is geen veilig alternatief. Daarbij kwam ook de problematiek kijken dat Arduino geen betrouwbare CA authenticatie heeft en kwetsbaar is voor “man in the middle attacks”. Na het voorleggen van deze problemen en de risico's bij de stagementors van Digipolis is het gebruik van een Arduino en PowerShell geschrapt voor dit project. Het gebruik van PowerShell op een apparaat dat kwetsbaar is voor netwerk intrusies en opslagen van Binaire netwerk certificaten is een te groot veiligheidsrisico. 

De tweede stap in het project was het testen van meer intelligente hardware. Hiervoor kwam de Raspberry Pi Zero en de Raspberry Pi 3B in aanmerking. De Raspberry Pi Zero kwam al snel niet meer in aanmerking omdat het opstellen van een volwaardige test setup extra kosten met zich zou meebrengen. Zo heeft de Raspberry Pi Zero op het moment van het onderzoek geen interne WiFi module. De aankoop van een WiFi shield en extra onderdelen die nodig zijn om een prototype te bouwen zorgde ervoor dat de prijs van een Raspberry Pi 3B voordeliger was. Tijdens het uitwerken van dit project is de Rarspberry Pi Zero W op de markt verschenen. Deze zou een interessante kandidaat zijn voor dit project. Wegens de beperkte tijd voor dit project komt de Raspberry Pi Zero W niet meer in aanmerking. De Raspberry Pi 3B geeft het project meer mogelijkheden naar de toekomst toe om te evolueren. Zo kan er gekozen worden voor een Linux of Windows IoT .NET Core besturingssysteem. De netwerkbeveiligingsstandaard is ook veel beter omdat de Raspberry Pi 3B een volwaardig besturingssysteem heeft. Verder kunnen er naar de toekomst toe ook meer intelligente sensors worden aangesproken zoals camera's en displays. In de toekomst zou een camera bijvoorbeeld gebruikt kunnen worden om zitplaatsbezetting op te volgen in de vergaderzaal. Een interactief display zou de boeking van de zaal kunnen weergeven en gebruikers de mogelijkheid geven om een vergaderzaal op lokatie te boeken voor een toekomstige vergadering. Digipolis is gebonden aan een strenge wetgeving en privacy beleid. Daarom is het gebruik van een camera in dit project niet van toepassing. 

Het project begint nu langzaam vorm te krijgen. Voor het project worden er 2 identieke prototypes gebouwd. Het huidige prototype is gebaseerd op een Rasberry Pi 3B die aan het 220V stroomnetwerk wordt gekoppeld. Op de Raspberry PI 3B wordt een Pythonscript gehost die de sensordata van de Passive Infrared Sensor (PIR) verzamelt. Het besturingssysteem van de Raspberry Pi 3B staat nog niet vast. De verzamelde data wordt via Message Queueing Telemetry Transport (MQTT) gepubliceerd en naar de lokale netwerk server die een Web service API in een Docker omgeving host. De Raspberry Pi 3B is de MQTT Publisher die de sensordata verzameld. Vervolgens ontvangt de MQTT Broker op de server de sensor telemetrie data. De Web service API vergelijkt de ontvangen sensor data van de MQTT Broker met de vergaderzaal reservering op Exchange Server. In dit project is de server van de Web service API zowel de MQTT Broker als de MQTT Subscriber. Dezelfde condities van die voorheen werden bepaald voor het PowerShell script, worden hier ook gebruikt. De ontvangen activiteitdata wordt vergeleken met de datum en tijd van de reservering. Zo weet de Web service API of er iemand in de vergaderzaal zit. Als in het begin van een reservering of na een periode wanneer de vergadering begonnen is, er geen activiteit plaats vindt, dan kan de Web service API de reservering annuleren. Zo kan de beschikbaarheid van de vergaderzalen meer optimaal benut worden. De Web service API bewaart alle realtime data in een JSON file in plaats van een PostgreSql server. De .JSON file wordt opgeslagen op de lokale Digipolis S3 DataLake of verwerkt door de NSX analysedienst van Digipolis. 

Het project is nu in een onderzoek fase om de sensor array nog uit te breiden. Door het toevoegen van een temperatuur, vochtigheidsgraad en een geluidssensor in een vergaderzaal. Deze extra sensors kunnen ook een bijdragen leveren door het in kaart brengen van de vergaderomgeving. De geluidssensor zou een tweede controlepunt zijn om activiteit in een vergaderzaal te detecteren. De geluidssensor neemt geen audio op maar zal enkel dienen om geluid boven 30 Decibel vast te stellen. Deze verzamelde data kan bijdragen tot het in kaart brengen van de bezetting en atmosferische omstandigheden bij korte en langdurige vergaderingen. De volgende stap is de software op punt stellen. Dit houdt in dat op de Raspberry Pi 3B een Pythonscript voor het beheren van de sensors en een MQTT Publisher applicatie draait. Voor de netwerk server wordt er een Web Service API ontwikkeld die in Docker is gehost. De Web service API dient als basestation om alle sensors gegevens te centraliseren. 

### Realisaties 
<!--Korte oplijsting gedane werk zowel onderzoek, analyse als realisaties.-->
* Testen Arduino UNO met PIR
* Testen Arduino Featherwing HUZZAH met PIR
* Testen Arduino UNO met WizzFi shield met WiFi WPA2-PEAP Enterprise
* Testen Arduino Featherwing HUZZAH met Wifi WPA2-PEAP Enterprise
* Onderzoek Raspberry Pi Zero
* Test: Raspberry Pi 3B met PIR & WiFi
* Test: Hosten van sensor data op Raspberry Pi 3B local webserver
### Huidige werkpunten
<!--Beschrijven wat de huidige focus punten zodat er progressie is in de BAP/Stage-->
* Ontwikkelen van een Web service die een communicatie brug vormt tussen de Raspberry pi 3B en de exchange server
 * single point of failure.
 * Web service hosten in docker
 * Web service deployen via Bamboo
* Ontwikkelen software om de sensors op de Raspberry Pi 3B aan te sturen. 

### Toekomst
<!--Mogelijk richting naar waar de BAP/Stage kan evolueren in de toekomst-->

* Omzetten van een theoretisch project naar de praktijk
* Het project uitbreiden van 2 prototypes naar heel het gebouw
* Het aantal sensors op het systeem uitbreiden 

## Extra informatie
### Bijscholingen
<!--Bijgewoonde seminaries, presentaties, workshops, bedrijfsbezoeken etc in deze periode (onderwerp, datum, korte samenvatting en beoordeling)-->
### Seminaries
* Infosessie: Form en Survey Engine
* Infosessie: IoT MEC Onderzoek naar luchtkwaliteit in Antwerpen
### Sprint reviews
* Sprint Review: Sorteerstraat & Parkeersensors
### Vergaderingen
* Vergadering: Luchtkwaliteit in het gebouw
* Vergadering: Evacuatie plan Digipolis
* Vergadering: Automatisering stroom onderbreking in vergaderzalen

### Nieuwe contacten
<!--Nieuwe contacten gemaakt in deze periode (naam, voornaam, e-mail, telefoonnummer, bedrijf, functie, relevantie voor het werk)-->

### Literatuur
<!--Nieuwe contacten gemaakt in deze periode (naam, voornaam, e-mail, telefoonnummer, bedrijf, functie, relevantie voor het onderzoek)-->
