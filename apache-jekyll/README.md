First build the Jekyll image

```
cd jekyll
sudo docker build -t foofoo/jekyll:v1 .
sudo docker images
cd ..
```

Next setup the Apache image

```
cd apache
sudo docker build -t foofoo/apache:v1 .
cd ..
```

Build a jekyll instance and push a sample website to it

```
# the absolute path to `example` is needed
sudo docker run -v $PWD/example/:/data/ --name foo_blog foofoo/jekyll:v1
```

Build the apache instance using the jekyll volume

```
sudo docker run -d -P --volumes-from foo_blog --name foo_apache foofoo/apache:v1
```

now to find the IP address of the website

```
sudo docker port foo_apache 80
```


if we want to clean up everything that is not running or being used:

```
sudo docker system prune -a
```
