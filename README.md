## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Update the path with the name of your diagram](https://app.diagrams.net/#G1ryqNMJ9E0sp3i7DwR_Rn9tuZz7N6hOUE)LINK to diagram or embed image) 

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

Enter the playbook file._ Screen Shot 2021-07-29 at 8.52.50 PM

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable and secure, in addition to restricting non-secure traffic/requests to the network.
-What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
-What does Filebeat watch for? Filebeat collects data about the file system. In the case of this project the Filebeat allows us to search for specific information in files and visualize it using Kibana.
-What does Metricbeat record? Metricbeat collects machine metrics. In the case of this project Metricbeat allows us to search for specific information regarding metrics of our machines and visualize it using Kibana.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name        | Function   | IP Address | Operating System |
|-------------|------------|------------|------------------|
| Jumpbox     | Gateway    | 10.0.0.4   | Linux            |
| Web 1       | Web Server | 10.0.0.5   | Linux            |
| Web 2       | Web Server | 10.0.0.6   | Linux            |
| Elk Machine | ELK Server | 10.0.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Whitelist IPs
Client Machine 174.52.116.16

Machines within the network can only be accessed by SSH into Jumpbox.
Elk Server, Web 1 and Web 2 can only be accessed through SSH into Jumpbox.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |     No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because every time you need to configure a new machine you can use the ansible/YAML file with the same settings and specifications increasing redundancy and reliability and saving time by rolling out the same settings to multiple machines at once. 

The playbook implements the following tasks:
- In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...Install Docker.io
-...Install Python script
-...Install Python Docker Module
-...Download and launch docker web container


\
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _web 1 10.0.0.4 and web 2 10.0.0.5

We have installed the following Beats on these machines:
-Filebeat, Metricbeat and Packetbeat

These Beats allow us to collect the following information from each machine:
- _Filebeat collects file information like logs, Metricbeat collects metrics that are visualized with Kibana and Packetbeat collects the packets sent from and to the machine.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Yamlplaybook file to ansible.
- Update the Yaml file to include IP address of machine you are adding
- Run the playbook, and navigate to the Kibana dashboard to check that the installation worked as expected.

 Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? The Yaml files is copied into the ansible container.
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? You specify by adding that machine's IP address
- _Which URL do you navigate to in order to check that the ELK server is running? http://[your.VM.IP]:5601/app/kibana
_
