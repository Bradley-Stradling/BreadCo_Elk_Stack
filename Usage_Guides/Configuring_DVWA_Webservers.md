# Configuring_DVWA_Webservers.md

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/DVWA/Snip_1.png?raw=true)

Running the playbook with the command "ansible-playbook /path/to/deploywebservers.yml".

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/DVWA/Snip_2.png?raw=true)

Should then be able to ssh to each webserver box and curl the local host for the dvwa setup html.
"curl localhost/setup.php"

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/DVWA/Snip_3.png?raw=true)

We should then be able to access the DWVA page via the public ip of our load balancer.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/DVWA/Snip_4.png?raw=true)
