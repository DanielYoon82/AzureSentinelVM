<h1>Apply Filters to SQL Queries</h1>

<h2>Description</h2>
I built a SOC in Azure using a virtual machine as a honeypot. The data from log in attempts was forwarded to a central repository in Sentinel for observation. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>KQL and Sentinel</b> 

<h2>Environments Used </h2>

- <b>Windows 10 and Sentinel</b> (21H2)

<h2>Program walk-through:</h2>


- <b>Viewing logs in security events</b> <br />
First, I viewed the logs in my VM ensuring events have taken place.  <br/>
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLfla.jpg" height="77%" width="77%" alt="Disk Sanitization Steps](https://github.com/DanielYoon82/AzureSentinelVM/blob/main/images/LogRepository1.jpg)"/>
</p>
<br />                                                                                                                                                    
<br />

- <b>Create a log repository</b> <br/> <br />
Configuration of a log repository was made to forward virtual machine logs within. <br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLLogInAttempts.jpg" height="75%" width="75%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />

- <b>Configuration of security events in Sentinel</b> <br />
Installation of security events for further configuration and efforts in connecting my VM to the log analytics workspace. <br/>
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLMX.jpg" height="73%" width="73%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />

- <b>Querying log repository with KQL</b> <br />
A query using KQL searching for "SecurityEvent" was made to observe general logs.  <br/>
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLeM.jpg" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />

- <b>Applying specific KQL queries</b> <br />
To narrow the search results, I applied "where" in "EventID" for event "4625." Specifically, "TimeGenerated, Account, Computer, EventID, Activity, IpAddress" further narrowed down the search to filter results of interest. <br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLFS.jpg" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />

- <b>Geolocation data upload to SIEM</b> <br/>
A spreadsheet containing geolocation of IP addresses was uploaded to provide mapping ranges.<br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLnoIT.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />

- <b>Sentinel workbook for map</b> <br/>
A new workbook within sentinel was created using a data from a json file. Data was then copy and pasted for a new query.<br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLnoIT.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />

- <b>Creation of attack map</b> <br/>
As a result, an attack map showing logs from around the world illustrated where events had taken place.<br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLnoIT.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />

- <b>Summary</b> <br />
I demonstrated using Azure with modeling a VM to open up the network of cloud firewall to the internet. The data in the log repository was then forwarded to the log analytics workspace as a central repository. A spreadsheet containing geo data was implented in Sentinel (SIEM) to monitor log in activity using KQL filters. Finally, the result illustrated on a world map showing these events.
<br />
<br />
