###Raspberry Pi 3B en Python 3
<p style="text-align: justify;">
Het project startte met een Arduino UNO en een eenvoudig script in C/C++. Naarmate het project vorderde, is het project tot zijn recht gekomen door gebruik te maken van een Raspberry Pi 3B. De functionaliteit met de PIR sensor en de Raspberry werkt. Er was een probleem met het verzenden van de data naar NSX. Hierdoor liep het project vast. De strakke beveilingsnormen van Digipolis en de NSX RabbitMQ MQTT Broker zorgden voor problemen. Dit maakte het debuggen van de het Python3 script andere configuratie instellingen een traag en pijnlijk proces. Lokale testen waren wel succesvol, maar zodra dezelfde test doorging in de omgeving met enterprice security liep het mis. Voor een gebruiker zoals ik, met beperkte toegankelijkheid tot de configuratie van achterliggende netwerk infrastructuur, geen toegang hebbend tot certificaten voor het draadloos netwerk en andere beveiligingsprotocollen van het netwerk, maakt dat het afstellen en debuggen van software en hardware zeer moeilijk te verwezelijken is.</p>