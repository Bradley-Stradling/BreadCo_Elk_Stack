# Configuring Ansible

First we will need to add the local IP's of our machines intended for deployments to their respective groups in the "/etc/ansible/hosts" file.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/Ansible/Snip_1.png?raw=true)

We will also need to add our username to the etc/ansible/ansible.conf file as well. 

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/Ansible/Snip_2.png)

We should then be able to ping all machines, if you have an ssh password set you will need to ping them one at a time.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/Ansible/Snip_3.png)
