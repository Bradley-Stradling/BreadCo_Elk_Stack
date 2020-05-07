# BreadCo_Elk_Stack

********************************************************************************
 (\\\_/)                Author: Bradley Stradling                          (\\\_/)
 (o.o)       Title: Automated ELK Stack Deployment for BreadCo.          (*.*)
(")\_(")             Lincense: https://unlicense.org/                    (")\_(")
********************************************************************************

The files in this repository were used to configure the network deployment 
depicted below.

(Images/Network_Diagram.png)
(Images/Firewall_Settings.png)

All machines were spun up using Azure's provided Linux (ubuntu 18.04) operating 
system.

| Machine                  | Function  | VN IP Address | Container           |
|--------------------------|-----------|---------------|---------------------|
| JumpToBreadCoWebServices | Gateway   | 11.11.11.4    | ansible             |
| BreadCoWebServer1        | Webserver | 11.11.11.5    | cyberxsecurity/dvwa |
| BreadCoWebServer2        | Webserver | 11.11.11.6    | cyberxsecurity/dvwa |
| BreadCoWebServer3        | Webserver | 11.11.11.7    | cyberxsecurity/dvwa |
| BreadCoWebServer4        | Webserver | 11.11.11.8    | cyberxsecurity/dvwa |
| BreadCoElkStack          | ELKServer | 11.11.11.9    | sebp/elk            |

These files have been tested and used to generate a live ELK deployment on Azure. 
They can be used to recreate the entire deployment pictured above. 

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use## Automated ELK Stack Deployment for BreadCo.
  - Machines Being Monitored
- List of files used
- How to Use the Ansible Build

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored 
instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly redundant.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for 
changes to the systems. Filebeat exports logs from the webservers to the ELK server 
so that they can be presented and parsed by Kibanna through an accessed webpage.

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpToBreadCoWebServices machine can accept connections from the Internet.
Access to this machine is only allowed from designated IP addresses.

Machines within the network can only be accessed by JumpToBreadCoWebServices.

The webpage access to the ELK machine is only allowed by designated IP addresses.
A summary of the access policies in place can be found in the table below.

| Machine                  | Public Access | Allowed IP addresses |
|--------------------------|---------------|----------------------|
| JumpToBreadCoWebServices | Yes           | 11.11.11.5-9         |
| BreadCoWebServer1        | No            | None                 |
| BreadCoWebServer2        | No            | None                 |
| BreadCoWebServer3        | No            | None                 |
| BreadCoWebServer4        | No            | None                 |
| BreadCoElkStack          | ELK page only | None                 |

### WebServer Configuration

Ansible was used to automate configuration of the webservers.
No configuration is performed manually to allow for easy expandability.

The deploywebservers.yml playbook implements the following tasks:
- Installs docker to the webservers.
- Installs the dependancy "pip" to the webservers.
- Downloads installs and starts the dwva webserver container.

The deployfilebeattowebservers.yml playbook implements the following tasks:
- Downloads filebeat-7.4.0-amd64.deb to the webservers.
- Installs filebeat to the webservers.
- Drops in the filebeat.yml config file.
- Enables the filebeat modules system.
- Runs the filebeat setup command.
- Starts the filebeat services.

### Elk Configuration

Ansible was used to automate configuration of the ELK machine as well. 
Again, no configuration is performed manually to allow for easy expandability.
Though there is only 1 elk server in this configuration, as the playbook could
install and start multiple elk servers at once the plural is used.

The deployelkservers.yml playbook implements the following tasks:
- Installs docker to the elkservers.
- Installs the dependancy "pip" to the elkservers.
- Increases virtual memory to that which elk requires.
- Downloads and launches the elk docker container with the needed ports.

The following screenshot displays the result of running `docker ps` after 
successfully configuring the ELK instance.

(Images/Docker_PS_Output)

### Target Machines & Beats
This ELK server is configured to monitor the webserver machines.

We have installed the following Beats on these machines:

These Beats allow us to collect the following information from each machine:

### Using the Playbooks
In order to use the playbooks, you will need to have an Ansible control node 
already configured. Assuming you have such a control node provisioned: 
