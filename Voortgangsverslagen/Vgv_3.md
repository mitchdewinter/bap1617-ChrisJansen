# Voortgangsverslag #3
#  Titel onderwerp: Smartbuildings @ Digipolis: De bezettingsgraad van conferentieeruimtes optimaliseren
## Promotors
<!--Zet hier alle namen+email van je verschillende promotors (stagebegeleider, stagementor). Zeker in vet zetten indien er veranderingen hebben plaatsgevonden-->

* **Stagebegeleider**
  * Maarten Luyts - Maarten.Luyts@ap.be
* **Stagementor**
  * Greet Brosens - Greet.Brosens@Digipolis.be
  * Rudi De Geest - Rudi.deGeest@Digipolis.be
* **Stagegever** (Stage coördinator Digipolis)
  * Stijn Matthe - Stijn.Matthe@Digipolis.be
* **Stagecoördinators**
  * Maarten Luyts - Maarten.Luyts@ap.be
  * Marc Smets - Marc.Smets@ap.be
## Abstract
<!--Het abstract is een samenvatting van je totale bachelorproef, inclusief reeds gekende resultaten-->

Het IoT project van het automatisch vergaderzaalbeheer in Exchange server 2016 is stapsgewijs tot stand gekomen. Hiervoor is het project gestart met een goedkope technologie en een simpele autonomie zoals de Arduino Uno microcontroller en een Passive Infrared Sensor (PIR) om activiteit in een vergaderzaal te detecteren. Naarmate het project vorderde is het project geëvolueerd naar het gebruik van meer intelligente hardware zoals de Rasberry PI 3B om aan de projecteisen te voldoen. Op de Raspberry Pi draait het Raspbian operating systeem. De hardware werd verder uitgebreid met PIR Sensoren en Led. De software werd aangevuld met Mosquito MQTT (broker client) en python3. Hard- en software zijn in staat om in eerste instantie bewegingen te detecteren wat de aanwezigheid van mensen verondersteld. In de toekomst kunnen er DHT22 sensoren toegevoegd worden. Sensoren die de temperatuur alsook de vochtigheidsgraad meten en software die deze gegevens interpreteren zullen de dataset verrijken in de toekomst. 
Tijdens deze fase van het project worden de technieken (zowel hardware als software) bestudeerd, geëvalueerd en bijgestuurd met de resultaten van de uitgevoerde testen. Op die manier wordt het proces steeds verfijnd en worden werkende deelprojecten gerealiseerd. 

Voor dit piloot project wordt gemeten op welke momenten er beweings activiteit in de zaal aanwezig is. In de toekomst kan door het toevoegen van een DHT22 senoser als aanvulling op de sensor array de temperatuur en de vochtigheidsgraad van de zaal ook worden in kaart gebracht.

## Technische omschrijving
<!--Technische omschrijving van de evolutie van het project tijdens de betrokken periode, met aanduiding van de reeds bekomen resultaten en een planning voor de verdere uitwerking, welke problemen zijn ondervonden en hun oplossingen:-->
<!--Minimum 2000 woorden-->

Het automatisch beheren van het vergaderzalenproject is stapsgewijs tot stand gekomen. Tijdens de ontwikkeling van het project zijn er veel technologieën aan bod gekomen. In eerste instantie lag de focus op het essentiële gebruik van de sensors en het aanspreken naar de Exchange server. De Arduino Uno Rev.3 en een Passive Infrared Sensor (PIR) is gebruikt om activiteit in een vergaderzaal te detecteren. De Arduino microcontroller geeft sensordata draadloos door aan een server die een PowerShell script host. Hiervoor maakt de Arduino controller gebruik van een zelfstandige ESP8266 Wifimodule. Het PowerShell script controleert op de Exchange server of de vergaderzaal gereserveerd is door de Exchange Web Service API (EWS) aan te spreken. Zo vergelijkt het script de datum/tijd van de reservatie met de ontvangen sensordata. Als het script de eerste 30 minuten van de vergadering of 20 minuten nadat de vergadering is begonnen geen activiteit detecteert in de vergaderzaal, zal het script de reservering van de vergadering op de Exchange Server annuleren. Zo kan de vergaderzaal door iemand anders opnieuw geboekt worden. De events die het script onderneemt, zou worden bijgehouden in een PostgreSql databank. De databank verzamelt informatie over de bezetting en de redenen waarom de reservatie van de vergaderzaal is geannuleerd. Het eerste probleem dat zich voordeed bij het testen van het eerste prototype was de verbinding van de Arduino aan het WiFi netwerk van Digipolis. Deze gebruikt WPA2-Enterprise PEAP-MSSHAPv2 encryptie. Voor het project zijn er drie opstellingen getest. De eerste was een Arduino Uno met externe ESP8266 wifi module, de tweede een Arduino Uno met WizzFiShield en de derde een Arduino Featherwing HUZZAH. Tot op heden van dit project is de ondersteuning van Enterprise encryptie voor Arduino echter beperkt. Als oplossing voor dit probleem kan een Root Certificaat binair op de Arduino geplaatst worden. Maar dit is geen veilig alternatief. Daarbij kwam ook de problematiek kijken dat Arduino geen betrouwbare CA authenticatie heeft en kwetsbaar is voor “man in the middle attacks”. Na het voorleggen van deze problemen en de risico's bij de stagementors van Digipolis is het gebruik van een Arduino en PowerShell geschrapt voor dit project. Het gebruik van PowerShell op een apparaat dat kwetsbaar is voor netwerk intrusies en opslagen van Binaire netwerk certificaten is een te groot veiligheidsrisico en onaanvaardbaar voor Digipolis. 

De tweede stap in het project was het testen van meer intelligente hardware. Hiervoor kwam de Raspberry PI Zero en de Raspberry PI 3B in aanmerking. De Raspberry PI Zero kwam al snel niet meer in aanmerking omdat het opstellen van een volwaardige test setup extra kosten met zich zou meebrengen. Zo heeft de Raspberry PI Zero op het moment van het onderzoek geen interne WiFi module. De aankoop van een WiFi shield en extra onderdelen die nodig zijn om een prototype te bouwen zorgde ervoor dat de prijs van een Raspberry PI 3B voordeliger was. Tijdens het uitwerken van dit project is de Rarspberry PI Zero W op de markt verschenen. Deze zou een interessante kandidaat zijn voor dit project. Wegens de beperkte tijd voor dit project komt de Raspberry PI Zero W niet meer in aanmerking. De Raspberry PI 3B geeft het project meer mogelijkheden naar de toekomst toe om te evolueren. Zo kan er gekozen worden voor een Linux of Windows IoT .NET Core besturingssysteem. De netwerkbeveiligingsstandaard is ook veel beter omdat de Raspberry PI 3B een volwaardig besturingssysteem heeft. De Raspberry PI 3B heeft zowel een draadloze Wifi als een wired Ethernet verbinding. Verder kunnen er naar de toekomst toe ook meer intelligente sensors worden aangesproken zoals camera's en displays. In de toekomst zou een camera bijvoorbeeld gebruikt kunnen worden om zitplaatsbezetting op te volgen in de vergaderzaal. Een interactief display zou de boeking van de zaal kunnen weergeven en gebruikers de mogelijkheid geven om een vergaderzaal op lokatie te boeken voor een toekomstige vergadering. Digipolis is gebonden aan een strenge wetgeving en privacy beleid. Daarom is het gebruik van een camera in dit project niet van toepassing. 

Het project begint nu langzaam vorm te krijgen. Voor het project worden er 2 identieke prototypes gebouwd. Het huidige prototype is gebaseerd op een Rasberry PI 3B die aan het 220V stroomnetwerk wordt gekoppeld. Op de Raspberry PI 3B wordt een Pythonscript gehost die de sensordata van de Passive Infrared Sensor (PIR) verzamelt. Het besturingssysteem van de Raspberry PI 3B staat nog niet vast. De verzamelde data wordt via Message Queueing Telemetry Transport (MQTT) gepubliceerd en naar de lokale netwerk server die een Web service API in een Docker omgeving host. De Raspberry PI 3B is de MQTT Publisher die de sensordata verzameld. Vervolgens ontvangt de MQTT Broker op de server de sensor telemetrie data. De Web service API vergelijkt de ontvangen sensor data van de MQTT Broker met de vergaderzaal reservering op Exchange Server. In dit project is de server van de Web service API zowel de MQTT Broker als de MQTT Subscriber. Dezelfde condities van die voorheen werden bepaald voor het PowerShell script, worden hier ook gebruikt. De ontvangen activiteitdata wordt vergeleken met de datum en tijd van de reservering. Zo weet de Web service API of er iemand in de vergaderzaal zit. Als in het begin van een reservering of na een periode wanneer de vergadering begonnen is, er geen activiteit plaats vindt, dan kan de Web service API de reservering annuleren. Zo kan de beschikbaarheid van de vergaderzalen meer optimaal benut worden. De Web service API bewaart alle realtime data in een .JSON file in plaats van een PostgreSql server. De .JSON file wordt opgeslagen op de lokale Digipolis S3 DataLake of verwerkt door de NSX analysedienst van Digipolis.

Gaandeweg wordt er onderzocht of de sensoren aangevuld kunnen worden met andere meettoestellen of toepassingen. Tijdens de onderzoeksfase bleek dat het integreren van een microfoon voor het detecteren van geluid geen optie zou zijn. Enerzijds is de wetgeving op de privacy een beperkende factor. Anderzijds levert het slechts een beperkte winst op in de functionaliteit. Gezien de microfoon enkel gebruikt wordt om geluid te detecteren in de ruimte, zou het dezelfde ficntie opnemen als de PIR sensor (deze detecteert eveneens de aanwezigheid van objecten), wat geen meerwaarde levert aan het project. De PIR Sensor heeft voorrang op de microfoon gezien deze nagenoeg geen invloed heeft op de Privacywetgeving.  Het initiele prototype zal zich richten tot het implementeren van enkel een PIR sensor en de DHT22 sensor onder voorbehoud dat deze tijdig beschikbaar zal zijn voor de stage. De Raspberry PI 3B zal aangestuurd worden door Raspbian, een bestuuringssysteem dat de stabiliteit garandeerd voor langlopende projecten en waarvan het gebruiksgemak bewezen is. De sensoren worden gecontrolleerd door een Python script dat bij het opstarten van de Raspberry PI 3B automatisch data begint te vergaren. Deze data wordt doorgestuurd en bewaard bij de NXT RabbitMQTT Broker. Een webservice API, gehost in een Docker omgeving, zal de data ophalen bij NSX middels een MQTT subscription. Door het analyseren van de data en het te vergelijken met de reservaties op de Exchange server, kan er beslist worden of de vergaderzaal effectief in gebruik is. Bij een negatief antwoord kan de vergaderzaal vrijgegeven worden voor een volgende gebruiker. Hierdoor wordt de bezettingsgraad geoptimaliseerd. 

Op termijn kan het project worden uitgebreid naar meerdere vergaderzalen. De SD kaartjes met het Raspbian operating systeem zijn zeer makkelijk te dupliceren en ook het python script heeft maar een minimum aan configuratie nodig. Hierdoor dient de hostname, credentials en de MQTT per Raspberry PI 3B te worden bijgewerkt. Door de hostname als referentie te gebruiken kan de Raspberry PI 3B op het netwerk terug gevonden worden zonder dat deze beïnvloed wordt mocht er later een statisch of dynamic IP adress toegewezen moeten worden.

Tijdens het onderzoek zijn er veel problemen aan het licht gekomen. Zo diende er onderzocht te worden wat het meest geschikte besturingssysteem zou zijn voor de Raspberry PI 3B. Al snel bleek dat Windows IoT Core de meeste complicaties met zich mee bracht. ER bleken zich teveel conflicten voor te doen bij het  gebruik van Python scripts. Rasphian bleek een betere keuze gezien conflicten nagenoeg niet voorkomen. Een bijkomend voordeel is dat een Raspbian zeer gebruiksvriendelijk is en quasi letterlijk 'plug and play' bleek nadat de libraries geïmporteerd waren.

Bij de ontwikkeling van een ASP.NET Core webservice API in de Docker met een Windows 10 Home besturingsstysteem bleek dat een Windows 10 Pro versie een absolute noodzaak is. Voor de Windows 10 Home-versie is er een Docker "legacy" Toolbox met Docker engine 1.12 beschikbaar echter deze ondersteunt enkel ASP.NET projecten en niet de laatste ASP.NET Core. Docker for Windows met Docker engine 1.13 of hoger, ondersteund ASP.NET Core. Het was voor dit Digipolis-project van fundamenteel belang dat ASP.NET Core gebruikt werd. Docker vereist Hyper-V en container ondersteuning die alleen in Windows 10 Pro beschikbaar is. Hiervoor was het aankopen van een windows 10 Pro upgrade nodig.

Tijdens het testen van de Digipolis EventHandler ASP.NET Core template moest deze ook gemigreerd worden naar een nieuwe versie van Visual Studio. Het project zit nu in het stadium van integratie en ontwikkeling van de webservice API en het bouwen van de MQTT-brug tussen de Raspberry PI 3B en de webservice tamplate voor een feilloze overdracht van data. De volgende stap is het ophalen van de gegevens bij de exchange server en deze te vergelijken met de door NSX verzamelde gegevens.

Tijdens het testen is het moeilijk om de verzonden data naar NSX te verifiëren zonder toegang te hebben tot het NSX analytisch protaal. Een test-account is aangevraagd maar nog niet beschikbaar. In de huidige situatie moet bij iedere test NSX gecontacteerd worden per e-mail of telefonisch om de resulaten van de test te controleren. Dit is niet progressief en een tijdrovend proces.

Na de onderzoeks fase is gebleken dat dat een microfoon voor geluids detectie niet zo gewenst is. Omwillen van de wetgeving en de beperkte winst in functionaliteit. Omdat de microfoon enkel en alleen zou gebruikt wordne voor het detecteren van een geluids volume indicatie zou deze dezelfde functie hebben als de PIR sensor. Dit maarkt één van de twee sensors overbodig. De PIR sensor heeft hier het voordeel omdat deze de wet van de privacy minimaal aantast. Het initiele prototype zal zich richten tot het implementeren van enkel een PIR sensor en de DHT22 sensor onder voorbehoud dat deze tijdig beschikbaar zal zijn voor de stage. Om de Raspberry Pi 3B te beheren is er gebruik gemaakt van Raspbian omdat dit besturing systeem het gebruiks gemak en de stabiliteit garandeerd voor lange lopende projecten. De sensors worden gecontrolleerd door een python script dat bij opstarten van de Raspberry automatisch data begint te vergaren. De verzamelde data wordt on the fly doorgestuurt en bewaard bij de NXT RabbitMQTT Broker. Een webserviceAPI die wordt gehost in een Docker omgeving zal de data weer ophalen bij NSX via een MQTT subscription. Door de ontvangen data op zijn beurt te vergelijken met de reservaties van de Exchange server  kan een besluit gevormd worden om een gereserveerde vergaderzaal vrij te geven of niet.

Naar de toekomst toe kan dit project worden geupscaled naar meerdere vergader zalen. De SD kaartjes met het Raspbian operating systeem zijn zeer makkelijk te clonenen en het python script heeft maar een minimum aan configuratie nodig. Hierbij moet de hostname, credentials en de MQTT per Raspberry worden bijgewerkt. Door de hostname als referentie punt te gebruiken kan de Raspberry op het netwerk worden terug gevonden zonder dat dit beinvloed word mocht het nodig zijn in de toekomst van een statisch of dynamic IP adress toe te wijzen.

Tijdens het onderzoek process zijn er veel problemen aan bod gekomen. Bij het onderzoek stadium dat moest weergeven wat het meest intressantste besturing systeem zou zijn voor de Raspberry Pi tijdens dit project bleek dat Windows IoT Core de meeste complicaties met zich mee bracht. Een veel voorkoment probleem was dat er zich onnodig veel conflicten voordeden bij het gebruik van Python scripts. Dit was niet het geval bij Raspbian waar het bijna letterlijk plug en play was nadat de libraries geimporteert zijn.

In voorbereiding van naar het ontwikkelen van een ASP.NET Core webservice API in de Docker  windows 10 home omgeving bleek al snel dat hiervoor een Windows 10 Pro versie voor nodig is. Voor Windows home is er een Docker "legacy" Toolbox met Docker engine 1.12 beschikbaar maar deze ondersteunt enkel ASP.NET projecten en niet de laatste ASP.NET Core. Docker for Windows met Docker engine 1.13 of hoger,  ondersteund ASP.NET Core. Het was voor dit Digipolis project fundamenteel van belang dat ASP.NET Core gebruikt werd. Docker vereist Hyper-V en container ondersteuning die alleen in Windows 10 Pro beschikbaar is. Hiervoor was het aankopen van een windows 10 Pro upgrade nodig.

Bij het testen van de Digipolis EventHandler ASP.NET Core template moest deze ook gemigreerd worden naar een nieuwe versie van Visual Studio. Het project zit nu in dit stadium van integratie en ontwikkeling van de webservice API en het opstellen van de MQTT brug tussen de Raspberry PI 3B en de webservice tamplate. De volgende stap is het ophalen van de gegevens bij de exchange server en deze te vergelijken met de door NSX verzamelde gegevens. 

Tijdens het testen is het moeilijk om de verzonden data naar NSX te ferifyeren zonder toegang te hebben tot NSX analitisch protaal. Een test account is aangevraagd maar tot op heden nog niet beschikbaar. In de huidige situatie moet bij iedere test NSX gecontacteerd worden per e-mail of telefonisch om de resulaten van de test te controleren. Dit is niet progressief en een heel tijd consumerend process.




### Realisaties 
<!--Kort oplijsting gedane werk zowel onderzoek, analyse als realisaties.-->

* onderzoek
	* MQTT credentials en encryptie
	* Docker 'Legacy' toolbox vs Dcoker for Windows
	* Windows Home vs Windows Pro voor het gebruik van Docker
	* compatibliteit van Visual Studio 2013 vs 2017 in de Digipolis development omgeving
* analyse
	* versturen van MQTT naar NSX met encryptie
	* ASP.NET Core ontwikkeling in Docker 'Legacy' toolbox
* realisaties
	* werkent Raspberry PI 3B prototype met 8 pins PIR-STD Sensor
	* Ondersteuning voor MQTT
	* Opzetten van Visual Studio en Dcoker omgeving
	* Voorbereiden van ASP.NET Core template
	
### Huidige werkpunten
<!--Beschrijven wat de huide focus punten zodat er progressie is in de BAP/Stage-->

* Huidige focus van stage is het verbinden van de Raspberry PI 3B met webservice API waarbij de NSX RabbitMQTT Broker optreedt als bemiddelaar.

* Het grootste gedeelte van het BAP onderzoek is intussen afgerond. Nu is het van belang dat het voorafgaande onderzoek in de praktijk wordt omgezet en getest wordt in de realiteit. Hiervoor moeten echter nog toestemmingen gevraagd en toegekend worden. Ook zal het project nog door het acceptatieproces van Development geloodst moeten worden waar het project grondig getest zal worden alsvorens dit in productie kan worden geïntegreerd.

* De omkadering van de onderzoeksvraag is vastgelegt en het prototype is gebouwd. Nu is de volgende stap het uitwerken van de software voor de raspberry en de webservice-API. 

### Toekomst
<!--Mogelijk richting naar waar de BAP/Stage kan evolueren in de toekomst-->
* In de evolutie van de BAP naar de toekomst toe zal het project na development in acceptatie getest worden.

Het project zal gedurende een proefperiode in productie draaien.

Als de resultaten van de proefperiode gunstig zijn, zal het project ook worden uitgebreid naar andere vergaderzalen.

## Extra informatie
### Bijscholingen
<!--Bijgewoonde seminaries, presentaties, workshops, bedrijfsbezoeken etc in deze periode (onderwerp, datum, korte samenvatting en beoordeling)-->

### Nieuwe contacten
<!--Nieuwe contacten gemaakt in deze periode (naam, voornaam, e-mail, telefoonnummer, bedrijf, functie, relevantie voor het werk)-->

* Sven Jochems <sven.jochems@nsx.normalizedsystems.org>
	* Bedrijf: NSX
	* Java Developer
	* Relevantie: Contact persoon voor het opstellen van de MQTT broker bij Digipolis/NSX

### Literatuur
<!--Nieuwe contacten gemaakt in deze periode (naam, voornaam, e-mail, telefoonnummer, bedrijf, functie, relevantie voor het onderzoek)-->