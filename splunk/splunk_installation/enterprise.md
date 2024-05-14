## Make sure to install the basic linux packages first
[Basic linux config](../../linux/clean_install.md)

## Install splunk
```
cd /opt

wget -O splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz "https://download.splunk.com/products/splunk/releases/9.2.1/linux/splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz"

tar -xf splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz 
rm splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz

useradd --home-dir /opt/splunk splunk --shell /bin/bash

chown -R splunk:splunk /opt/splunk 
su splunk
```