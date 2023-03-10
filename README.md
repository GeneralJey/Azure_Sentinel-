<h1>Microsoft Azure Sentinel (SIEM)</h1>




<h2>Description</h2>
The project consists of a custom PowerShell script to extract metadata from Windows Event Viewer to be forwarded to third-party API to derive geolocation data. Configuring Log Analytics Workspace in Azure to ingest custom logs containing geographic information (latitude, longitude, state, and country) and configuring custom fields in Log Analytics Workspace with the intent of mapping geo data in Azure Sentinel and configuring Azure Sentinel (Microsoft Cloud SIEM) workbook to display global attack data (RDP brute force) on a world map according to the physical location and magnitude of attacks.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Microsoft Sentinel</b>
- <b>Microsoft Defender for Cloud</b>
- <b>Log Analytics Workspace</b>

<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Azure Cloud Computing</b>
- <b>Virtual Machine</b>
- <b>IP Geolocation API</b>


<h2>Project walk-through:</h2>

<p align="center">
Virtual Machine Deployment (HoneyPot VM) <br/>
<img src="https://imgur.com/i72JdLm.png" height="55%" width="55%" alt="Virtual Machine Deployment"/>
<br />
<br />
Creating Firewall Rules to Allow Any Trafict (HoneyPot VM) <br/>
<img src="https://imgur.com/4Eq2vWm.png" height="55%" width="55%" alt="Creating Firewall Rules"/>
<br />
<br />
Creating Log Analytics Workspace <br/>
<img src="https://imgur.com/RB79w0D.png" height="55%" width="55%" alt="Creating Log Analytics Workspace"/>
<br />
<br />
Microsoft Defender for Cloud Log Enviroment Created <br/>
<img src="https://imgur.com/QMpvl11.png" height="55%" width="55%" alt="Microsoft Defender for Cloud Log Enviroment Created"/>
<br />
<br />
Activating Microsoft Defender and Cloud Security Posture Management <br/>
<img src="https://imgur.com/CXiAPFD.png" height="55%" width="70%" alt="Activating Microsoft Defender and Cloud Security Posture Management"/>
<br />
<br />
Connecting the HoneyPot VM on Azure Dashboard <br/>
<img src="https://imgur.com/VLKiK0l.png" height="55%" width="70%" alt="Connecting the HoneyPot VM on Azure Dashboard"/>
<br />
<br />
Using RDP to Connect with the HoneyPot VM <br/>
<img src="https://imgur.com/x3crNFT.png" height="55%" width="70%" alt="Using RDP to Connect with the HoneyPot VM "/>
<br />
<br />
Event Viewer Inside the HoneyPot VM <br/>
<img src="https://imgur.com/F6w8b98.png" height="55%" width="70%" alt="Event Viewer Inside the HoneyPot VM"/>
<br />
<br />
Using the API to Get Geo Data<br/>
<img src="https://imgur.com/H2qlWd5.png" height="55%" width="70%" alt="Using the API to extract Geo Data"/>
<br />
<br />
Creating Custom PowerShell Script to extract Geo Data from the API and Create a Custom Log File <br/>
<img src="https://imgur.com/vwBGfVz.png" height="60%" width="70%" alt="Creating Custom PowerShell Scrip to extract Geo Data from the API and Crear a Custom Log File"/>
<br />
<br />
Raw Data Extracted from the Custom Log <br/>
<img src="https://imgur.com/BVv2BEp.png" height="70%" width="70%" alt="Raw Data Extracted from the Custom Log"/>
<br />
<br />
Creating a Custom Log (Log Analytics Workspace Azure) <br/>
<img src="https://imgur.com/jgVateF.png" height="70%" width="70%" alt="Creating a Custom Log on Log Analytics Workspace (Azure)"/>
<br />
<br />
Creating Field Values <br/>
<img src="https://imgur.com/ADphsax.png" height="55%" width="70%" alt="Creating Field Values"/>
<br />
<br />
Training AI with Raw Data from the Custom Log (Part 1) <br/>
<img src="https://imgur.com/Yvfq1Ny.png" height="70%" width="70%" alt="Training AI with Raw Data from the Custom Log 1"/>
<br />
<br />
Training AI with Raw Data from the Custom Log (Part 2) <br/>
<img src="https://imgur.com/JMbqjg9.png" height="70%" width="70%" alt="Training AI with Raw Data from the Custom Log 2"/>
<br />
<br />
Custom Log After Adding New Fields and AI Training <br/>
<img src="https://imgur.com/jG4WSkP.png" height="70%" width="70%" alt="Custom Log After Adding New Fields and AI Training"/>
<br />
<br />
Creating Log Query <br/>
<img src="https://imgur.com/CRGfvCw.png" height="70%" width="70%" alt="Creating Log Query"/>
<br />
<br />
Hot Map Showing RDP Brute Force Attacks by Geolocation <br/>
<img src="https://imgur.com/L4BeSkJ.png" height="70%" width="70%" alt="Hot Map Showing RDP Brute Force Attacks by Geolocation"/>
<br />
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
