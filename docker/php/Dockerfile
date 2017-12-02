FROM php:7.1-fpm

# Update
RUN apt update

# Install recommended extensions for Symfony
RUN apt-get install -y \
        apt-utils \
        libicu-dev \
        git \
        vim \
        zsh \
        autoconf \
        zip \
        unzip \
        openssl
 
 RUN docker-php-ext-install \
        intl \
        opcache \
        pdo \
        pdo_mysql

# Permission fix
RUN usermod -u 1000 www-data  

# Install Oh my Zsh
RUN bash -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
RUN sed -i -- 's/robbyrussell/kafeitu/g' /root/.zshrc # Other awesome theme: random kafeitu sonicradish wezm+

# Add Config
ADD .zshrc /root

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# Install the Symfony Installer
RUN curl -LsS http://symfony.com/installer -o /usr/local/bin/symfony
RUN chmod a+x /usr/local/bin/symfony