# ElkStack

The purpose of this repositor is to show you the files and process needed to creact and Elk Stack. An Elk Stack is a combination of the tools Elasticsearch, Kibana, Beats, and Logstash.


configuration.yml
filebeat-playbook.yml
metricbeat-playbook.yml
install_elk.yml
This document contains the following details:

Description of the Topology
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly redundant, in addition to restricting access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system metrics.

Filebeat monitors log files for locations that can be specified by a system administrator. Filebeat can then be used to forward and aggregate all relatable data to a centralized location

Metricbeat can be utilized to record metrics and statistics in respect to each service being run on various systems. Similarly, Metricbeat will send all data to a centralized location for ease of monitoring.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system metrics.

The configuration details of each machine may be found below.

Name	Function	IP Address	Operating System
Host OS	Workstation	73.151.102.152	Windows 10
Jump-Box	Gateway	10.0.0.4	Ubuntu Server
ELK-VM	Elk Stack	10.1.0.4	Ubuntu Server
Web-VM1	DVWA Server	10.0.0.5	Ubuntu Server
Web-VM2	DVWA Server	10.0.0.6	Ubuntu Server
Web-VM3	DVWA Server	10.0.0.7	Ubuntu Server
Access Policies
The machines on the internal network are not exposed to the public Internet.

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

73.151.102.152
Machines within the network can only be accessed by the Jump Box.

*** ELK-VM also accepts public connections but only from 73.151.102.152

A summary of the access policies in place can be found in the table below.

Name	Publicly Accessible	Allowed IP Addresses
Jump-Box	Yes	73.151.102.152
ELK-VM	Yes	73.151.102.152 & 10.0.0.4
Web-VM1	No	10.0.0.4
Web-VM2	No	10.0.0.5
Web-VM3	No	10.0.0.6
Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because automation allows for the quick configuration of multiple containers. This allows both rapid elasticity as well as scalability.

The playbook implements the following tasks:

Configure elk with Docker
Increase virtual memory
Use more memory
Install Docker.io
Install Python3-pip
Install Python Docker Module
Download and launch a Docker Web Container
