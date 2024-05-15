#### put the apps or user config in these folders
```
$SPLUNK_HOME/etc/shcluster/
     apps/
          <app-name>/
          <app-name>/
          ...
     users/
```
``` 
cd /opt/splunk/etc/shcluster/apps
mkdir test_deployer_app
cd test_deployer_app
mkdir default
mkdir local
cd local 
touch app.conf
echo "# app.conf config succesfully deployed from deployer" >> app.conf
```
#### run the deploy command if searchheads are ready to receive

```
/opt/splunk/bin/splunk apply shcluster-bundle -target <URI>:<management_port> -auth <username>:<password>
```

This will deploy the config on one server and if everything is configured right the cluster heads will 
share the config amongst eachother. 

example 
```
/opt/splunk/bin/splunk apply shcluster-bundle -target https://192.168.2.2:8089 -auth admin:Admin123!
```

Now you can find the app deployed on the searchheads in /opt/splunk/etc/apps

!troubleshooting:

- Make sure the secret key of the deployer and the indexer is matching 
- Make sure you are not targetting the deployer, you should target a searchhead. 
- Make sure you are using https not http in the URI
- Make sure The deployer and searchheads are running when executing the command.