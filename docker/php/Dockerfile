FROM php:8.3-fpm 

RUN apt-get update \ 
&& apt-get install -y --no-install-recommends \ 
    ca-certificates \ 
    curl \ 
    openssl \ 
    git \ 
    unzip \
    openssh-client \ 
    libpq-dev \ 
    libzip-dev \ 
&& update-ca-certificates \ 
&& docker-php-ext-install pdo_pgsql zip \ 
&& rm -rf /var/lib/apt/lists/* 

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer 
WORKDIR /var/www/html 