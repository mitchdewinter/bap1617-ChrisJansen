# Logboek Week #2 (6/2/17 - 10/2/17)
### Maandag
* Maken van flowchart voor het vergadersysteem.
* Onderdelen zoeken om PIR sensor prototype te bouwen.
* Library & documentatie zoeken om Featherwing HazzaH aan het wifi netwerk te koppelen.
### Dinsdag
* Afwerken flowchart en blokschema.
* Maken van technische tekening voor PIR sensor.
* Installeren CP210x USB to UART Bridge VCP Drivers om met featherwing te communiceren.
* Vergadering sync sensoren.
  * Mogelijkheid tot systeem automatisch aankondiging bij evacuatie op PA systeem.
  * Procedure intercom bij evacuatie.
  * Mogelijkheid tot het meten van luchtkwaliteit in het gebouw.
  * Systeem om de aanwezige afdelingsverantwoordelijke te lokaliseren bij evacuatie.
* Vergadering wekelijkse evaluatie.
  * Linux devomgeving Docker in Node.js of Microsoft .NET Core.  
  * Opstellen prijslijstje onderdelen van prototype.
  * Bestellen nog vermiste componenten.
  * Prioriteit bouwen prototype.
* Flowchart & architectuur diagram aanpassen.
### Woensdag
* Experimenteren met IDE's.
  * Arduino IDE:
     * werkt het beste
     * is meer gedocumenteerd 
  * NodeMCU/Lua 
* Maken van componenten lijst voor bestelling.
* Maken van testopstelling met PIR sensor en led om detectie weer te geven.
 * Probleem GPIO willen led niet doen oplichten.
     * Oorzaak, slecht contact op het breadboard.
 * Probleem bij tesen van PIR: Serial console geeft alleen war tekens.
     * Geprobeerd door het aanpassen van baudrate   
     * Geprobeerd met andere scripts
     * Geprobeerd met andere PIR sensors 
     * Geprobeerd met nieuwe booltloader

### Donderdag
* Maken van breadboard schema van sensor module. (klaar).
* Maken van technisch schema van sensor module. (klaar)
* Maken van PCB schema van sensor module. (klaar)
### Vrijdag
* Debuggen van PCB schema.
* Prototype PIR response testenPIR reageert, 5 seconds delay time van laatste detectie tot standby mode.
* Opzoeken van Feather HuzzaH compatibiliteit met WPA2-Enterprise PAEPs.