FROM ubuntu:xenial
MAINTAINER bronsoms

ENV DEBIAN_FRONTEND noninteractive
ENV COMPOSER_DISABLE_XDEBUG_WARN 1

RUN apt-get update && \
    apt-get install -y --allow-unauthenticated apache2 php7.0 php7.0-mysql php7.0-intl php7.0-xml libapache2-mod-php7.0 curl composer unzip bash-completion && \
    apt-get autoremove -y && \
    apt-get clean && \
    apt-get autoclean

# Enable apache mods.
RUN a2enmod php7.0
RUN a2enmod rewrite

# Manually set up the apache environment variables
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid

# Expose apache.
EXPOSE 80

# Configure Virtualhost
ADD templates/000-default.conf /etc/apache2/sites-enabled/000-default.conf

# Configure bash
ADD templates/.bashrc /root/.bashrc

# By default start up apache in the foreground, override with /bin/bash for interative.
CMD /usr/sbin/apache2ctl -D FOREGROUND

# Set working dir
WORKDIR /var/www
