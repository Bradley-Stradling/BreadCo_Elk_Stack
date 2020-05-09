# Configuring Metric Beats

You will need to adjust the src and dst path for the filebeat.yml file to get the playbook to deploy the file correctly.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/Metric_Beats/Snip_1.PNG?raw=true)

Adding the address of our elk server to send the logs to. (metricbeat.yml)
The password should be changed after you have everything going later as well.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/Metric_Beats/Snip_2.PNG?raw=true)

## Need to add the ip of our kibana and port.(metricbeat.yml)

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/Metric_Beats/Snip_3.PNG?raw=true)

Running the playbook.
-"ansible-playbook /path/to/deployfilebeattowebservers.yml"

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/Metric_Beats/Snip_4.PNG?raw=true)

If successful we should see logs coming into kibana on our elk interface page.

![](https://github.com/Bradley-Stradling/BreadCo_Elk_Stack/blob/master/Images/Metric_Beats/Snip_5.PNG?raw=true)
