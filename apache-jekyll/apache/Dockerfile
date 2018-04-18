FROM ubuntu:17.10
MAINTAINER Zebulun Arendsee <zbwrnz@gmail.com>
ENV REFRESHED_AT 2018-04-13

# install apache
RUN apt-get -yqq update
RUN apt-get -yqq install apache2

# setup the volume where the website will be hosted
VOLUME [ "/var/www/html" ]

# set the working directory
WORKDIR /var/www/html

# set up the environment
ENV APACHE_RUN_USER  www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR   /var/log/apache2
ENV APACHE_PID_FILE  /var/run/apache2.pid
ENV APACHE_RUN_DIR   /var/run/apache2
ENV APACHE_LOCK_DIR  /var/lock/apache2

# make required files
RUN mkdir -p $APACHE_RUN_DIR $APACHE_LOCK_DIR $APACHE_LOG_DIR

EXPOSE 80

ENTRYPOINT [ "/usr/sbin/apache2" ]

CMD ["-D", "FOREGROUND"]
