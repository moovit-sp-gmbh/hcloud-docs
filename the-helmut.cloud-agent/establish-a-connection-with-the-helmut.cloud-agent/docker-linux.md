# Docker (Linux)

In a Docker environment, you can use this example compose file to set up a helmut.cloud Agent in a container.

```
// Example compose file

version: '3.8'
 
services:
  hcloud-agent:
    image: dckr.hlmc.io/moovit-sp-gmbh/hcloud-agent:latest
    ports:
      - "6968:6968"
    volumes:
      - hcloud-agent:/root/.hcloud
    restart: unless-stopped
    
 
volumes:
  hcloud-agent:
    /myhostshare:/mycontainershare

```

The connection(s) for a Docker HCloud agent is (are) defined via the clients configuration page:

```
http://docker-client-ip:6968/agent/
```
