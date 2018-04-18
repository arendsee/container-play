# Playing with containers

This is a personal repo for messing around with containers, such as Docker.

## Archlinux instructions

```
sudo pacman -S docker
sudo systemctl start docker.service
```

### Example 1 - a bash shell

```
sudo docker run -i -t ubuntu /bin/bash
```

This will look for a local 'ubuntu:latest' image, if not found it will attempt to pull it:


```
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
22dc81ace0ea: Pull complete
1a8b3c87dba3: Pull complete
91390a1c435a: Pull complete
07844b14977e: Pull complete
b78396653dae: Pull complete
Digest: sha256:e348fbbea0e0a0e73ab0370de151e7800684445c509d46195aef73e090a49bd6
Status: Downloaded newer image for ubuntu:latest
root@ab5be44c47c9:/# echo hello world
hello world
root@ab5be44c47c9:/#
```

And now I am in a docker shell

```
sudo docker run -it ubuntu /bin/bash
```


### Demons

```
sudo docker run --name "captain_hotblade" -d ubuntu /bin/sh -c "while true; do echo hi; sleep 1s; done"
sudo docker top captain_hotblade
sudo docker inspect captain_hotblade
sudo docker stop captain_hotblade
sudo docker kill captain_hotblade
sudo docker rm captain_hotblade
```


### Search and pull

```
sudo docker search jamptur01/puppetmaster
sudo docker pull jamptur01/puppetmaster
```

### Building a new image

Two approaches: commit and Dockerfile, the latter is better


### Logging in

```
sudo docker login
```
