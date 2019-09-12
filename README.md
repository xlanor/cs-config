## Settings used for a docker-compose deployment of code-server

### Pre-Requisite
* [local-persist](https://github.com/MatchbookLab/local-persist)
* docker-ce
* docker-compose

Generate nginx keys using 
> openssl dhparam -dsaparam -out /etc/nginx/ssl/dhparam.pem 4096

I kind of forgot where I took this docker-compose config from... can't find it.
Anyway, 
```
  ports:
    - 8443:8443
```
Leave the internal one as 8443, change the first one to whatever port is on the host.


```
  jingkai_cs_data: 
    driver: local-persist
    driver_opts: 
      mountpoint: /home/jingkai/code-server/cs_data
  jingkai_cs_settings:
    driver: local-persist
    driver_opts:
      mountpoint: /home/jingkai/code-server/cs_settings
```

This persists your settings, ext, so on so forth.
Create the mountpoint before running.
