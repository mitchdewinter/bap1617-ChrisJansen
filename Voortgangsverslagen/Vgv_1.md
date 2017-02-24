# Voortgangsverslag #1
# Titel onderwerp: IoT-Smartbuildings: Het automatisch beheren van vergaderzalen met sensoren en Exchange server.

## Promotors

* **Stagementor:**
    * Maarten Luyts - Maarten.Luyts@ap.be
* **Stagepromotor:**
    * Greet Brosens - Greet.Brosens@Digipolis.be
    * Rudi De Geest - Rudi.deGeest@Digipolis.be

## Onderwerp
### Abstract
Een veel voorkomend probleem bij Digipolis te Antwerpen is dat de gereserveerde tijd van vergaderzalen niet altijd volledig benut wordt. In vele gevallen komen de mensen ook niet opdagen zonder dat de reservering van de vergaderzaal geannuleerd wordt of een vergadering is vroegtijdig gedaan. Daardoor gaat er veel vergaderruimte verloren, ook al is er veel vraag naar. In sommige gevallen worden lege vergaderruimtes vrijblijvend gebruikt zonder reservaties. Dit zorgt in bepaalde gevallen dat gereserveerde ruimtes niet beschikbaar zijn vlak voor het aanvangen van een geboekte vergadering.
### Doel
Het doel van dit Bachelorproject is een oplossing te zoeken voor het automatisch beheren van vergaderzalen bij Digipolis. Dit door middel van Internet of Things toe te passen in de vorm van Smart Buildings. De lokalen kunnen met een detectiesysteem worden uitgerust. Hierdoor kan een vergaderzaal gecontroleerd worden op activiteit. Indien er niemand op komt dagen of deze vroegtijdig terug beschikbaar is, kan de reservering na het niet detecteren van beweging gedurende een periode worden geannuleerd. Dit kan worden gerealiseerd door gebruik te maken van passieve warmtesensoren die de vergaderzalen controleren op beweging. Indien er geen activiteit wordt vastgesteld gedurende een gegeven aantal minuten zal de vergaderzaal terug worden vrijgegeven. Publieke vergaderzalen kunnen uitgerust worden met een LED indicatiesysteem dat weergeeft of de vergaderruimte vrij, gereserveerd of bezet is.
### Resultaat
Het eindresultaat van dit Bachelorproject is het ontwikkelen van een realistische oplossing om de vergaderzalen automatisch te kunnen beheren en het opleveren van een prototype. Het gehele project moet flexibel, te beheren en schaalbaar zijn. De registratie module bestaat uit een Raspberry Pi 3B met een PIR sensor. De Raspberry Pi 3B communiceert met een web service die de kalender op de Exchange server aanspreekt. 
### Analyse
Tijdens de onderzoekfase van het project zijn er al enkele aspecten aan het licht gekomen. Hierbij komt kijken dat er toch een minimum standaard van de hardware gevraagd wordt. Het belang van beveiliging van het netwerk en de privacy tijdens een vergadering lopen hier voorop. Minder intelligente hardware zoals Arduino's zouden perfect kunnen dienen om de sensors aan te sturen. Echter deze voldoen niet aan de eisen die de beveiliging aan de hardware stelt. Het gebruik van meer intelligente hardware zoals Raspberry Pi 3B of Raspberry Pi Zero geeft meer flexibiliteit. De Raspberry Pi 3B is door zijn connectiviteit zoals onboard Ethernet, Wi-Fi en Bluetooth ook makkelijker te beheren. Dit maakt de hardware voor dit project ook een betere investering om deze in de toekomst voor andere projecten te gebruiken. De bedoeling is dat het systeem aan het 220V net gekoppeld wordt. Omdat het gebruik van batterijen een onderhoudkost met zich meebrengt. Onder bepaalde omstandigheden is het ook een risico tijdens brand. Het gebruik van Lithium batterijen in een kantoorplafond kan voor onverwachte, mogelijk explosieve situaties zorgen in geval deze aan kortsluiting of aan vlammen worden blootgesteld. Daarom is de keuze gevallen op de Raspberry Pi 3B om een prototype te bouwen.
### Roadmap
Om dit project te realiseren heb ik volgende Roadmap samengesteld:

* Week 05 30/01-03/02: Inkadering stage project
* Week 06 09/02-10/02: Onderzoek Hardware en Technologieën
* Week 07 13/02-17/02: Onderzoek Security protocol van het netwerk
* Week 08 20/02-24/02: Uitwerken abstract en analyse
* Week 09 27/02-03/03: Uitwerken van technische schema's van het prototype
* Week 10 06/03-10/03: Aanvragen van Developers privileges en Developer environment instellen
* Week 11 13/03-17/03: Bouwen van prototype Raspberry Pi 3B + Sensor
* Week 12 20/03-24/03: Configureren van het Raspberry Pi 3B
* Week 13 27/03-31/03: Ontwerpen beheer software voor sensors
* Week 14 03/04-07/04: Ontwerpen van web services naar Exchange server
* Week 15 10/04-14/04: Programmeren van sensors over het netwerk
* Week 16 17/04-21/04: Debuggen van software
* Week 17 24/04-28/04: Testen van software en hardware in de praktijk
* Week 18 01/05-05/05: Evaluatie van testen en mogelijke aanpassingen
* Week 19 08/05-12/05: Scriptie controleren
* Week 20 15/05-19/05: Voorbereiden prototype
* Week 21 22/05-26/05: Samenstellen portfolio & scriptie
* Week 22 29/05-02/06: Bundel controleren en overlopen
* Week 23 06/06-09/06: Deadline portfolio
## Keywords
* Internet of Things
* Smart buildings
* Conference rooms
* MS Exchange Server 2016
* Raspberry Pi 3B
* PIR Sensors
* Automatisering
## Milestones
* Inkaderen van de opdracht
* Uitwerken van de analyse
* Bouwen van 2 prototypes
* Ontwikkelen van de sensor software
* Ontwikkelen van de web service software
* Testen van de software samen met de hardware
* De testopstelling omzetten naar een praktijkomgeving.