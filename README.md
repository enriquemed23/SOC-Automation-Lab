# SOC Automation Lab

## Objective
The SOC Automation Lab project aimed to establish a controlled environment for simulating, detecting, and responding to cyber incidents. The primary focus was to use a Security Information and Event Management (SIEM) platform in conjuction with Security Orchestration, Automation, and Response (SOAR) capabilities and being able to manage these incidents with a streamline incident response workflow and case management. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

Wazuh will generate an alert for Mimikatz usage on a system. It will send this to our automation platform Shuffle.io and request enrichment based on file hash from VirusTotal. It will then forward this information to our case management platform TheHive. It will also send an email to an analyst.  It will also send back incident response information to Wazuh to perform that action on the system involved. 


## Skills Learned
- Deepended understanding of creation and configuration of a Security Information and Event Management (SIEM) platform
- Implementing SOAR capabilities
- Integrating multiple security tools and platforms for streamlined incident response
- Automating incident response actions based on alert severity and context
- Implementing automated enrichment of security alerts using VirusTotal API
- Leveraging email notifications for alerting security analysts

### Tools Used
- Wazuh, an Open Source SIEM system for log ingestion and analysis.
- System Monitor, a system service created to enhance logging and monitoring capabilities
- Shuffle.io, open-source SOAR platform for information security workflow automation
- VirusTotal, free online threat intelligence service for verification of malicous files
- TheHive, open-source security incident response platform for case management
- Digital Ocean, Cloud Provider

## Steps
Network Map to showcase workflow and utilizaiton of all tools involved. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/NetworkMap.PNG"  /> <br> <br>
Used Win 10 Host VM with Sysmon installed from <a href="https://github.com/enriquemed23/Detection-Lab/tree/main">Detection Lab</a>
<img src="https://github.com/enriquemed23/Detection-Lab/blob/main/Sysmon install.PNG"  /> 
<img src="https://github.com/enriquemed23/Detection-Lab/blob/main/Sysmon confirmed.PNG" /> <br> <br>
Created a droplet (AKA VM) with Digital Ocean with Ubuntu 22.04 (LTS) x64.<br> Then used Putty to login and install Wazuh.<br> Logged into Wazuh web. 
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhDroplet.PNG" /> <img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhInstall.PNG" /> <img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhWeb.PNG" /> <br> <br>
Repeated same steps to create VM for TheHive. Installed all <a href="https://github.com/enriquemed23/Detection-Lab/tree/main">prerequisites</a> and reached TheHive web. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/theHiveInstall.PNG" /> <img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/TheHiveWeb.PNG" />
