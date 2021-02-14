## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  

https://github.com/Melissa00cole/project-1/blob/main/Diagrams/Red-Team-Network-Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Red-Team-network file may be used to install only certain pieces of it, such as Filebeat.

https://github.com/Melissa00cole/project-1/tree/main/Ansible

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure, in addition to restricting traffic to the network.
it will Protect applications from emerging threats · Authenticate User Access · Protect against DDoS attack · Simplify PCI compliance 
a jump boxes hidden benefit is that any tools in place for the SAN system are maintained on that single system. Therefore, when an update to the SAN management software is available, only a single system requires the update.A jump server is a hardened and monitored device that spans two security zones and provides a controlled means of access between them.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Network and system logs.
Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| web1     | server   | 10.0.0.9   | Linux            |
| web2     | server   | 10.0.0.10  | Linux            |
| web3     | server   | 10.0.0.9   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump-Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
50.53.171.220

Machines within the network can only be accessed by 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
Powerful. App deployment. Configuration management. Workflow orchestration. Orchestrate the app lifecycle.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/Melissa00cole/project-1/blob/main/Images/Docker_ps_output.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.9,10.0.0.10, 10.0.0.11

We have installed the following Beats on these machines:
filebeat-config.yml
filebeat-playbook.yml

These Beats allow us to collect the following information from each machine:
Filebeat,ships log files.
 Filebeat records the last successful line indexed in the registry, so in case of network issues or interruptions in transmissions, Filebeat will remember where it left off when re-establishing a connection
 
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ansible-configuraton file to Ansible
- Update the ansible.cfg file to include hosts.cfg 
- Run the playbook, and navigate to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
10.1.0.4:5601


_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
