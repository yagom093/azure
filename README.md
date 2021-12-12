Load balancing ensures that the application will be highly monitored, in addition to restricting flow of traffic to the servers
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?
Load balancers protects the system from DDoS attacks by directing traffic.
The advantage of a jump box is to give access to the user from a single node that can be secured and monitored while preventing any direct changes 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ a>
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remov>

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | VM       | 10.0.0.4   | Linux            |
| Web1     | VM/Docker| 10.0.0.5   | Linux            |
| Web2     | VM/docker| 10.0.0.6   | Linux            |
|Elk-Server| Server   | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowe>
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually>
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; downloa>
- ...
