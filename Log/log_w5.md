# Logboek Week #5 (27/02/17 - 03/03/17)
### Maandag
* Onderzoek Microsoft IoT Core software deployment
* Onderzoek Microsoft IoT Core webportaal
* Onderzoek Raspberry Pi 3N sensordata over netwerk zonder Azure
* Controleren technische schema's van Raspberry Pi 3B en  PIR sensor

### Dinsdag
* Installeren windows Windows Driver Kit
* Infosessie: Sprint review sorteerstraatje & parking sensors
* Onderzoek: Communicatie raspberry en exchange server* 
* Wekelijkse evaluatie
 * Architectuur afgewerkt
 * Technische schema's afgewerkt
 * Prototype afgewerkt
 * Visual Studio voorbereidingen afgewerkt
 * Docker moet nog geconfigureert worden
 * Sensor benaming  "sensor_DA2.x_Condor"
 * Opstellen Postgress SQL databank voor sensor events
* Onderzoek Raspberry Microsoft IoT Core communicatie met Exchange server 
  
### Woensdag
* Onderzoek Raspberry Pi code deployment naar meerdere Raspberries
* Testen van .NET Core template
Severity	Code	Description	Project	File	Line	Suppression State
  * Error	NU1002	The dependency Microsoft.NETCore.App 1.1.0 does not support framework .NETStandard,Version=v1.6.	Digipolis.Web	D:\APProject\sensor_manager\sensor_manager\src\Digipolis.Web\project.json	26 
  **Oplossing: interne nuget package tijdelijk niet beschikbaar**
  * Error	NU1001	The dependency dotnet-test-xunit >= 2.2.0-preview2-build1029 could not be resolved.	Digipolis.Web.UnitTests	D:\APProject\sensor_manager\sensor_manager\test\Digipolis.Web.UnitTests\project.json	17
  **Oplossing: Installeren package xunit.core en xunit.assert**
  * Error	NU1001	The dependency moq.netcore >= 4.4.0-beta8 could not be resolved.	Digipolis.Web.UnitTests	D:\APProject\sensor_manager\sensor_manager\test\Digipolis.Web.UnitTests\project.json	24	
  **Oplossing: interne nuget package tijdelijk niet beschikbaar**
  * Error	NU1001	The dependency xunit >= 2.2.0-beta2-build3300 could not be resolved.	Digipolis.Web.UnitTests	D:\APProject\sensor_manager\sensor_manager\test\Digipolis.Web.UnitTests\project.json	28	
 **Oplossing: interne nuget package 
 tijdelijk niet beschikbaar**
  * Error	NU1002	The dependency Microsoft.NETCore.App 1.1.0 does not support framework .NETStandard,Version=v1.6.	Digipolis.Web	D:\APProject\sensor_manager\sensor_manager\src\Digipolis.Web\project.json	26	
**Oplossing: interne nuget package tijdelijk niet beschikbaar**
 * Error		The project is configured to use .NET Core SDK version 1.0.0-preview2-003177 which is not installed or cannot be found under the path C:\Program Files\dotnet. These components are required to build and run this project. Download the version of .NET Core SDK specified in global.json or update the SDK version in global.json to the version that is installed.	Digipolis.Web	D:\APProject\sensor_manager\sensor_manager\src\Digipolis.Web\GETSDKTOOLINGINFO	1	
 **Oplossing: updaten versie in global.json**
 * Severity	Code	Description	Project	File	Line	Suppression State
Error	NU1001	The dependency dotnet-test-xunit >= 2.2.0-preview2-build1029 could not be resolved.	Digipolis.Web.UnitTests	D:\APProject\sensor_manager\sensor_manager\test\Digipolis.Web.UnitTests\project.json	17	
 **Oplossing: interne nuget package tijdelijk niet beschikbaar**

### Donderdag
* Voorbereiden .NET core template
* Onderzoek: PIR sensor deployment in de vergaderzalen
* Onderzoek: PostgreSql & PostgreSqlPure als databank voor het project.
* Verzamelen nieuwe grondplannen van Digipolis 2

### Vrijdag
* Installeren Docker
 * Probleem: Win 10 home (geen Hyper-V)
 * Oplossing: Docker legacy toolbox met virtualbox 
* Aanvraag BitBucket repository
* Configureren BitBucket repository
* Opzoeken toepassen vergaderzaal displays
 * Vrij, bezet, gereserveerd  