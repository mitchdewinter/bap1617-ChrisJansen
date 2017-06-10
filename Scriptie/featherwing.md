####2.1.1.2	Arduino Featherwing HUZZAH ESP8266
<img src="images/featherwing.png" alt="FIGUUR 3: ARDUINO UNO WIZFI210 SHIELD" width="200" height="" align="right">
<p style="text-align: justify;">Bij een volgende opstelling werd er gekozen om met een Arduino Featherwing HUZZAH te werken. De Arduino Featherwing HUZZAH is kleiner dan de Arduino UNIO en heeft een geintegreerde ESP8266 chipset. Ook hierbij controleert een script op de Exchange Server of de vergaderzaal gereserveerd is door de Exchange Web Service API (EWS) aan te spreken. Het schema ziet er dan als volgt uit:</p> 

![FIGUUR 4: ARDUINO featherwing HUZZAH EN PIR ARCHITECTUUR](images/architecturfeatherwing.png)

<p style="text-align: justify;">In tegenstelling tot de eerste testopstelling, werd er niet gewerkt met apparatuur gevoed door batterijen maar met apparaten die hun voeding uit netstroom halen.</p> 
<p style="text-align: justify;">Zoals eerder bleek, was de verbinding van de Arduino met het wifi netwerk van Digipolis een obstakel. Deze gebruikt WPA2-Enterprise PEAP-MSSHAPv2 encryptie. Een Arduino Uno met externe ESP8266 wifi module, blijkt geen waardig alternatief voor de eerste gefaalde proefopstelling gezien de ondersteuning van Enterprise encryptie voor Arduino eerder beperkt is.</p> 
<p style="text-align: justify;">Tijdens het overleg bleek dat het niet eenvoudig zou zijn om een goedkeuring te krijgen voor de eigengemaakte voeding (de voeding zou via netstroom verlopen en niet via batterijen zoals in de eerste opstelling). De procedure die gevolgd moet worden is te lang en waarschijnlijk niet haalbaar in deze stageperiode. Bovendien kunnen er geen veiligheidscertificaten voorgelegd worden en ontbreken doeltreffende betrouwbaarheidstesten voor de stepdownconverter die de veiligheidsrisico’s voor Digipolis tot nul moeten reduceren.</p>

![FIGUUR 4: ARDUINO featherwing HUZZAH EN PIR ARCHITECTUUR](images/featherwinghuzzahschemas.png)


<p style="text-align: justify;">Ook deze testopstelling krijgt een no-go. Enerzijds vergt het eigen PCB-design een lange procedure om tot een goedkeuring en een certificiëring te komen die quasi onmogelijk gerealiseerd kan worden binnen de periode van deze stage. Anderzijds blijft de externe ESP8266 wifi module problemen genereren bij het gebruik van Enterpise level encryptie.</p> 