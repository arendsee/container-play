FROM ubuntu:17.10
MAINTAINER Zebulun Arendsee <zbwrnz@gmail.com>
ENV REFRESHED_AT 2018-04-13

# Install everything needed for the jekyll website 
RUN apt-get -yqq update
RUN apt-get -yqq install ruby ruby-dev make nodejs gcc g++
RUN gem install --no-rdoc --no-ri jekyll

# Setup volumes
VOLUME [ "/data/", "/var/www/html" ]

# Set the working directory which will hold the website code
WORKDIR /data

# Set the entry point to automatically build whatever is found in WORKDIR into
# the site at /var/www/html
ENTRYPOINT [ "jekyll", "build", "--destination=/var/www/html" ]
