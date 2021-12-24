## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.



<figure><img src=/diagrams/diagram2.PNG><figcaption></figcaption></figure>

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the elk.yml file may be used to install only certain pieces of it, such as Filebeat.

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.


Load balancing ensures that the application will be highly monitored, in addition to restricting flow of traffic to the servers. Load balancers protect the system from DDoS attacks by redirecting traffic.
The advantage of a jump box is to give access to the user from a single node that can be secured and monitored while preventing any direct changes or attacks to any server or machine.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the configuration files and settings
- What does Filebeat watch for?
Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash
-  What does Metricbeat record?
Metricbeat is a shipper you can install on your servers to periodically collect metrics from the operating system and from services running on the server

The configuration details of each machine may be found below.

| Name     | Function | IP Address   |Operating System|
|----------|----------|--------------|----------------|                    
| Jump Box | VM       | 10.0.0.4     | Linux          |
| Web1     | VM/Docker| 10.0.0.5     | Linux          |
| Web2     | VM/docker| 10.0.0.6     | Linux          |
|Elk-Server| Server   | 10.1.0.4     | Linux          |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the Local machine can accept connections from the Internet.  Access to this machine is only allowed from the following IP addresses:
- 23.83.131.208

Machines within the network can only be accessed by SSH.

- Which machine did you allow to access your ELK VM? What was its IP address?
- Only my local machine was allowed to access the ELK VM and its IP address was 23.83.131.208. Other VMs that are in this network are allowed to SSH into the ELK server as well.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses                    |
|----------|---------------------|----------------------                   |
| Jump Box | No                  | 10.0.0.4-Virtual Network                |
| WEB 1 & 2| Yes                 | Virtual Network                         |
|Elk Server| No                  |23.83.131.208 - 10.1.0.4 - VirtualNetwork|

Each of the access policies listed above, are there to keep outside/unwanted access out and keep our projects safe. It only allows traffic from my local machine and then once I am in the Virtual Network I can SSH from one VM to the other and attach to dockers, ansibles, etc, if needed.


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because you can deploy multiple commands, changes, updates, etc, to multiple machines at once.

The playbook implements the following tasks:
Install: docker.io
Install: python-pip
Install: docker
Command: sysctl -w vm.max_map_count=262144
Launch docker container: elk

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

<figure><img src=/diagrams/elkserver.png><figcaption></figcaption></figure>

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
VM1 10.0.0.5
VM2 10.0.0.6

We have installed the following Beats on these machines:
Filebeat
Metricbeat

These Beats allow us to collect the following information from each machine:
Filebeat is a shipper used for forwarding and centralizing log data
Metricbeat is a shipper that you can install on your servers to collect metrics from the operating system and from services running on the server.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the filebeat-configuration.yml and install-elk.yml file to /etc/ansible/file.
- Update the host IP addresses in the config file to include the IP addresses of your web servers.
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? 
 /etc/ansible/file/filebeat-configuration.yml

- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
You would have to edit the /etc/ansible/host file and add the server ip addresses 

- _Which URL do you navigate to in order to check that the ELK server is running?
{IP ADDRESS}:5601/app/kibana

-As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
ansible-playbook {playbook you wish to run}
