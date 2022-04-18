# ELK_Stack

ELK Stack with Azure

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

*[Diagram]([Diagram]()) 

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the configuration and playbook yml file may be used to install only certain pieces of it, such as Filebeat.

*[Pentest]()

*[HOSTS]()

*[ELK-Playbook]()

*[Filebeat-Playbook]()

*[Metricbeat-Playbook]() 

*[Filebeat-Config]()”

*[Metricbeat-Config]()

*[Ansible-Config]()

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

| Name       | Function  | IP Address                  | OS     |
|-------- - -|--------- -|-----------------------------|--------|
| Jump Box   | Gateway   | 20.231.227.94/10.1.0.4      | Linux  |
| Web-1      | Server    | 20.121.87.226/10.1.0.5      | Linux  |
| Web-2      | Server    | 20.121.87.226/10.1.0.6      | Linux  |
| Web-3      | Server    | 20.1221.87.226/10.1.0.7     | Linux  |
| ELKserver  | Server    | 20.150.144.101/10.0.0.4     | Linux  |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the JumpBox_Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

- "<myworkstations>" PIP via TCP 5601

Machines within the network can only be accessed by "<myworkstation>" and JumpBox_Provisioner via SSH/Jumpbox_Provisioner.

- The ELK machine is accessable from the JumpBox_Provisioner's at 10.1.0.4 via SSH 22. Its IP address is "<myworkstation>"Public IP via TCP 5601

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible |              Allowed IP Addresses                  |
|----------|---------------------|----------------------------------------------------|
| Jump Box |Yes                  | 20.231.227.94 ("<myworkstation>" PubIP via SSH 22) |
| Web-1    |No                   | 10.1.0.4 SSH 22                                    |
| Web-2    |No                   | 10.1.0.4 SSH 22                                    |
| Web-3    |No                   | 10.1.0.4 SSH 22                                    |
| ELKserver|No                   | "<myworkstation>"  PubIP via TCP 5601              |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

- Automating configurations with Ansible makes deploying systems uniformed, reducing error, the need to spend time creating new custom code     and imporoving efficency.

The playbook implements the following tasks:

*Direct to machine

*Install Docker.io

*Install python3-pip

*Increase Virtual Memory

*Download and Launch Containers

*Ports to publish on

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

ElKServer

JumpBox Provisioner

| Web-1        | 10.1.0.5      
| Web-2        | 10.1.0.6      
| Web-3 (DVWA) | 10.1.0.7   


### Target Machines & Beats

This ELK server is configured to monitor the following machines:

-Web-1 - 

-Web-2 -

-Web-3(DVWA) -

We have installed the following Beats on these machines:

- Data Successful - Filebeat (see PNG)
- Data Successful - Metricbeat (see PNG)

These Beats allow us to collect the following information from each machine:
-one collects logs and one collects metrics/performance

### Using the Playbook

In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:

- Copy the .yml file to the ansible folder.
- Update the config file to include remote user name and ports
- Run the playbook, and navigate to Kibana:5601 to check that the installation worked as expected.
- Download the Filebeat playbook with curl -L -O to the /etc/ansible/filebeat-config.yml
- Update the filebeat-config.yml to include the ELK server private IP address from the ansible container.
- run the playbook with "Ansible-Playbook Filebeat-Playbook.yml"
- DO the same for the Metricbeat-Playbook and Metricbeat-Playbook (use port 9200)
- http://xx.xx.xxx.xxx:5601//app/kibana to check that the Elk server is running.

