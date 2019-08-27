# Virtualmin on Docker

Virtualmin installation on Ubuntu Bionic Beaver
(upgrade from techno-express/Virtualmin)

## Using docker-composer

```bash
## Assuming you already set the environment variables in .env file
$ docker-compose up -d
Creating network "virtualmin_virtualmin" with driver "bridge"
Creating virtualmin_mysql_1  ... done
Creating virtualmin_webmin_1 ... done
Creating virtualmin_redis_1  ... done
```

## Using docker run

```
docker run --name=hosting \
-v hosting-etc:/etc \
-v hosting-lib:/var/lib \
-v hosting-log:/var/log \
-v hosting-www:/var/www \
--hostname=server.virtualmin.host \
-p 10000:10000 -p 80:80 -p 443:443 \
--privileged --restart always -d anthonyhk/virtualmin
```

### Docker Hub
https://hub.docker.com/r/anthonyhk/virtualmin/builds automatically builds the latest changes into images which can easily be pulled and ran with a simple `docker run` command. 
