#### Create network in docker
```
docker network create --driver=bridge --subnet=192.168.2.0/24 --gateway=192.168.2.10 splunk-cribl-cloud
```

#### list available networks in docker
```
docker network ls
```

#### add node ubuntu node to existing network 
```
sudo docker run -itd --network=splunk-cribl-cloud --ip=192.168.2.1 --dns=8.8.8.8 --name SH1 --hostname SH1 -v /opt/SH/SH1:/opt ubuntu:latest
```

### Enter docker ubuntu node 
```
docker exec -ti SH1 bash
```