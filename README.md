# Vagrant & Docker Development Environment

A Vagrant development environment using docker internally

# Inside:

* Ubuntu 14.04
* Docker - Containers: nginx, php5-fpm, mysql, memcached, redis
* Docker Compose


# Why?
For a really quick development environment that uses docker internally, gets around the annoying lack of (easy) support of mounting local volumes using docker-machine allowing you to mount a local directory as your webroot but have an entirely self contained development environment.

# Requirements?

Vagrant & Virtualbox

# How?

    git clone git@github.com:voycey/cakephp-vagrant-docker.git && cd cakephp-vagrant-docker

Put your website files into ````www```` ensuring that the webroot folder is available at ````www/webroot```` (if you are using cakephp).
For any other framework / site ````DOCUMENT_ROOT```` is set to ````www/webroot```` so create that folder and place files in there and it all should work.

Edit ````docker-compose.yml```` and change ````MYSQL_DATABASE: forumapi_dev```` to the name of your database

Put your initial database dump into db-dumps (.sql files only) - these will automatically be imported into the MySQL database name you added above on provisioning

    vagrant up

**Get a coffee - this will take a while.**

When it has pulled everything down your site will be available at http://192.168.33.10 by default (You can change this in Vagrantfile)



