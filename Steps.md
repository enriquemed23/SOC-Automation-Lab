# Steps
## Network Map to showcase workflow and utilizaiton of all tools involved. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/NetworkMap.PNG"  /> <br> <br>
## Used Win 10 Host VM with Sysmon installed from <a href="https://github.com/enriquemed23/Detection-Lab/tree/main">Detection Lab</a>
<img src="https://github.com/enriquemed23/Detection-Lab/blob/main/Sysmon install.PNG"  /> 
<img src="https://github.com/enriquemed23/Detection-Lab/blob/main/Sysmon confirmed.PNG" /> <br> <br>

## Created a droplet (AKA VM) with Digital Ocean with Ubuntu 22.04 (LTS) x64. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhDroplet.PNG" /> <br>
## Then used Putty to login and install Wazuh. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhInstall1.PNG" /> <br>
## <br> Logged into Wazuh web. 
 <img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhWeb.PNG" /> <br> <br>
## Repeated same steps to create VM for TheHive. Installed all <a href="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/TheHiveInstall">prerequisites</a> and reached TheHive web. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/theHiveInstall.PNG" /> <img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/TheHiveWeb.PNG" /> <br><br>

Configuration files and changes to get TheHive and Wazuh communicating. 
-
**/etc/cassandra/cassandra.yaml** <br>
-cluster_name: **'thehivecluster'** <br>
-listen_address: **TheHivePublicIP** <br>
-rpc_address: **TheHivePublicIP** <br>
-seeds: **TheHivePublicIP**:7000 <br><br>

**/etc/elasticsearch/elasticsearch.yml** <br>
-cluster_name:**thehive** <br>
-Uncomment **node.name: node-1** <br>
-Uncomment **network.host: TheHivePublicIP** <br>
-Uncomment **http.port: 9200** <br> 
-Uncomment **cluster.intital_master_nodes: node-1** <br>
-Ensure that TheHive has ownership to important directory by **chown -R thehive:thehive /opt/thp** <br> <br>

**/etc/thehive/application.conf** <br>
-hostname = **["TheHivePublicIP"]** <br>
-cluster-name = **thehivecluster** <br>
-hostname = **["TheHivePublicIP]** <br>
-application.baseUrl = "http://**TheHivePublicIP**:9000" <br><br>

Wazuh Agent Configuration and Install.
-
## Wazuh generates the install command for you after a couple parameters. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhAgentWeb.PNG" /> <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhAgentInstall.PNG" /> <br>
## Wazuh agent config file is located at **C:\Program Files (x86)\ossec-agent** and added the following: 
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhAgentConf.PNG" /> <br>
## Wazuh has made contact with the agent. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhAgentConnected.PNG" /> <br><br>
## Create a rule in Wazuh to trigger on OriginalFileName to combat filename changes. 
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhRulesPage.PNG" /> <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhCustomRules.PNG" /> <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/WazuhMimiKatzRule.PNG" /> <br> <br>
## Renamed mimikatz to NewName to show obfuscation technique and to show how to catch it using the previously made rule. <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/MimikatzRenamed.PNG" /> <br>
<img src="https://github.com/enriquemed23/SOC-Automation-Lab/blob/main/MimikatzCaught.PNG" /> <br>
