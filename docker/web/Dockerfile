FROM ubuntu:xenial
MAINTAINER bronsoms

RUN PACKAGES_TO_INSTALL="sudo git cron php7.0 php7.0-intl php7.0-xml composer php-xdebug php7.0-zip php7.0-mbstring php7.0-curl php7.0-fpm php7.0-cli apache2 supervisor libyaml-dev php7.0-mysql iputils-ping" && \
    apt-get update && \
    apt-get install -y software-properties-common && \
    apt-add-repository -y ppa:ondrej/php && \
    apt-get update && \
    apt-get install -y --allow-unauthenticated $PACKAGES_TO_INSTALL && \
    apt-get autoremove -y && \
    apt-get clean && \
    apt-get autoclean

EXPOSE 80
