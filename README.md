<h1>Azure Sentinel Honeypot + Geo Attack Map</h1>

<h2>Description</h2>

This lab involved deploying a Windows 10 virtual machine in Microsoft Azure to act as a honeypot, capturing real-time unauthorized login attempts. Security logs were collected and forwarded to a centralized Log Analytics Workspace using the Azure Monitor Agent (AMA) and a configured Data Collection Rule (DCR).

The logs were queried using Kusto Query Language (KQL) to identify failed login attempts and monitor potential malicious activity. To enhance visibility, a custom IP geolocation dataset was uploaded to Sentinel as a Watchlist, allowing log entries to be enriched with geographic information.

An interactive attack map was created in Azure Sentinel Workbooks, visualizing the origin of failed login attempts in real time.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Kusto Query Language (KQL)</b> 
- <b>Azure Monitor Agent (AMA)</b>
- <b>Sentinel Watchlist</b>


<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019 </b>

<h2>Program walk-through:</h2>
