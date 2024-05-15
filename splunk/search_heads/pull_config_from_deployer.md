### Initialize cluster members

```
splunk init shcluster-config -auth <username>:<password> -mgmt_uri <URI>:<management_port> -replication_port <replication_port> -replication_factor <n> -conf_deploy_fetch_url <URL>:<management_port> -secret <security_key> -shcluster_label <label>
/opt/splunk/bin/splunk restart
``` 

#### example:

```
/opt/splunk/bin/splunk start
/opt/splunk/bin/splunk init shcluster-config -auth admin:Admin123! -mgmt_uri https://192.168.2.2:8089 -replication_port 8181 -replication_factor 3 -conf_deploy_fetch_url https://192.168.2.1:8089 -secret yoursecuritykey -shcluster_label shcluster
/opt/splunk/bin/splunk restart
```

- mgmt_uri is the searchhead itself, with the required mgmt port. <br>
- conf_deploy_fetch_url is the deployment server with the correct mgmt port.
- https niet http


#### Bring up cluster captain on a node of choice 
! include your own node in -serverlist as well 
```
splunk bootstrap shcluster-captain -servers_list "<URI>:<management_port>,<URI>:<management_port>,..." -auth <username>:<password>
```

#### example
```
/opt/splunk/bin/splunk bootstrap shcluster-captain -servers_list "https://192.168.2.2:8089,https://192.168.2.3:8089,https://192.168.2.4:8089" -auth admin:Admin123!
```

#### check the status of the cluster

```
/opt/splunk/bin/splunk show shcluster-status -auth admin:Admin123!
```
