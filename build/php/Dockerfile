FROM php:7-apache

# Maintainer
MAINTAINER XU Li<xuenru@gmail.com>

# Environments
ENV TIMEZONE	Europe/Paris

COPY php.ini /usr/local/etc/php/

# RUN
RUN cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime \
	&& echo "${TIMEZONE}" > /etc/timezone \
	&& apt-get update && apt-get install -y \
		libxml2-dev \
		libicu-dev \
	&& docker-php-ext-install intl pdo_mysql\
	&& docker-php-ext-enable opcache \
	&& a2enmod rewrite \
	&& docker-php-source extract \
	&& pecl install xdebug \
	&& docker-php-ext-enable xdebug \
	&& docker-php-source delete \
