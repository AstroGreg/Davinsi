

## Make sure to install the basic linux packages first
[Basic linux config](../../linux/clean_install.md)

## Install splunk
```
cd /opt

wget -O splunkforwarder-9.2.1-78803f08aabb-Linux-x86_64.tgz "https://download.splunk.com/products/universalforwarder/releases/9.2.1/linux/splunkforwarder-9.2.1-78803f08aabb-Linux-x86_64.tgz"

tar -xf splunkforwarder-9.2.1-78803f08aabb-Linux-x86_64.tgz 
rm splunkforwarder-9.2.1-78803f08aabb-Linux-x86_64.tgz

useradd --home-dir /opt/splunkforwarder splunkfwd --shell /bin/bash

chown -R splunkfwd:splunkfwd /opt/splunkforwarder 
su splunkfwd
```