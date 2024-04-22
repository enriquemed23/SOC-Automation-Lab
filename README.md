# SOC Automation Lab

## Objective
The SOC Automation Lab project aimed to establish a controlled environment for simulating, detecting, and responding to cyber incidents. The primary focus was to use a Security Information and Event Management (SIEM) platform in conjunction with Security Orchestration, Automation, and Response (SOAR) capabilities and being able to manage these incidents with a streamline incident response workflow and case management. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

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

## <a href="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/Steps.md">Steps</a>
