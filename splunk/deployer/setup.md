#### set server.conf key for deployer
```
echo "
[shclustering] 
pass4SymmKey = yoursecuritykey
shcluster_label = shcluster
deployer_push_mode = full
" >> /opt/splunk/etc/system/local/server.conf

/opt/splunk/bin/splunk restart

```
