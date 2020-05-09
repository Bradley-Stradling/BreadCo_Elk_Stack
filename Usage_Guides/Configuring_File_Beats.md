# Configuring_File_Beats.md

You will need to adjust the src and dst path for the filebeat.yml file to get the playbook to deploy the file correctly.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/File_Beats/Snip_1.png?raw=true)

Adding the address of our elk server to send the logs to. (filebeat.yml)
The password should be changed after you have everything going later as well.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/File_Beats/Snip_2.png?raw=true)

# Need to add the ip of our kibana and port.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/File_Beats/Snip_3.png?raw=true)

Running the playbook.
-"ansible-playbook /path/to/deployfilebeattowebservers.yml"

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/File_Beats/Snip_4.png?raw=true)

If successful we should see logs coming into kibana on our elk interface page.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/File_Beats/Snip_5.png?raw=true)
