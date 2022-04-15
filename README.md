# ELK_Stack
ELK Stack with Azure
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

 <https://github.com/abitalright/ELK_Stack/blob/a67bdccfdef307e4978d869ffaee8ed21a4d84aa/image/Diagram/1649881891426.png>

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

<https://github.com/abitalright/ELK_Stack/blob/5cbf8d08b93aabd0a05186b876b50996b709b496/Pentest.yml>
<https://github.com/abitalright/ELK_Stack/blob/5cbf8d08b93aabd0a05186b876b50996b709b496/hosts>
<https://github.com/abitalright/ELK_Stack/blob/5cbf8d08b93aabd0a05186b876b50996b709b496/elk-playbook.yml>
<https://github.com/abitalright/ELK_Stack/blob/5cbf8d08b93aabd0a05186b876b50996b709b496/filebeat-playbook.yml>
<https://github.com/abitalright/ELK_Stack/blob/5cbf8d08b93aabd0a05186b876b50996b709b496/metricbeat-playbook.yml>
<https://github.com/abitalright/ELK_Stack/blob/5ccdcadd407af12b43df1aee1cf0e14010834c37/filebeat_config.yml>
<https://github.com/abitalright/ELK_Stack/blob/5ccdcadd407af12b43df1aee1cf0e14010834c37/metricbeat_config.yml>
<https://github.com/abitalright/ELK_Stack/blob/e8449e6ea23da614509c0b864d75fb35ea285ca7/ansible_config.yml>

This document contains the following details:

- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly functional, in addition to restricting traffic to the network.  Load Balancers handle the routing of traffic from one server to another to ensure continutity of services delivery as well and provide service resiliancy against cyberthereats such as DDos attacks.  The load balancer with a jumpbox limit access to the entire network system and allow monitoring and reporting on the status of our services.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system logs.

- Filebeat watches for log files and forwards them on to Elasticsearch/Logstash for indexing.
- Metricbeat records metrics and statistics and forwards them on to Elasticsearch/Logstash for indexing.

The configuration details of each machine may be found below.
