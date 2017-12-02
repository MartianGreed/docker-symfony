**Docker starter for symfony**
===========
Configuration
------------

 - php-fpm
 - nginx
 - composer
 - mariadb

Installation
------------    
**&#35; Server configuration**

Before executing any command, go to the directory docker/nginx/ and create the file app.conf, a configuration example is provided with app.conf.dist.

In your app.conf, replace "symfony.dev" with your project url and edit hosts file to get named access to the web server:

    sudo vi /etc/hosts

Add the following line with your project url instead of "symfony.dev" :

    127.0.0.1 symfony.dev


Build the docker containers
------------ 
**&#35; Fresh start**

The first time, use the following command line :

    ./build

This will delete old instances, download if necessary and install new containers.

**&#35; Restart previous containers**

Use the following command line : 

	./up

**&#35; Containers configuration**

In the build and up script, every container is prefixed with "docker9", this can be changed, this prevents other docker configuration to override container with the same name.