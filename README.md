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

- <b>Windows 10</b>
- <b>Microsoft Azure </b>
- <b>Azure Sentinel </b>
- <b>Log Analytics Workspace </b>


<h2>Lab Overview:</h2>
<br />
<img src="https://i.imgur.com/Su9bFj7.png" height="80%" width="80%" />
<br />



1. **Create a Honeypot (vm)**: 
- Go to "Virtual Machines" in the Azure portal
- Deploy a Windows 10 VM
- Configure inbound rule in the Network Security Group to allow all traffic
- Disable Windows Firewall on the VM: Start → wf.msc → Properties → turn off all profiles
   <br />
   <br />
   
2. **Create a Central Log Repository (Log Analytics Workspace)**:
- Go to “Log Analytics Workspaces” and create a new workspace
- Name and link it to your subscription/resource group
   <br />
   <br />
   
3. **Connect Your VM to Log Analytics**:
- In the VM settings, go to “Extensions + Applications”
- Install the Azure Monitor Agent (AMA)
- Set up a Data Collection Rule (DCR) to forward security logs
- Ensure it's connected to the Log Analytics Workspace
<br />
<br />

4. **Query Security Logs with KQL**:
- Use Kusto Query Language (KQL) to investigate failed logins
- Observe timestamps, usernames, IPs, and more
<br />
<br />

5. **Upload Geolocation Data to Enrich Logs**: 
- Download the file: geoip-summarized.csv
- Go to Sentinel → Watchlist and upload as:
  - Name: geoip
  - Search Key: network
    
<br />
<br /> 

6. **Build an Attack Map Workbook**: 
- In Sentinel, create a new Workbook

- Remove default content and add a Query control

- run following query into the advanced editor

- Save and view real-time attack geolocation map
  
<br />
<br /> 
