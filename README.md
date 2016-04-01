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

    git clone git@github.com:voycey/vagrant-docker-lemp.git && cd vagrant-docker-lemp

Put your website files into ````www```` ensuring that the webroot folder is available at ````www/webroot```` (if you are using cakephp).
For any other framework / site ````DOCUMENT_ROOT```` is set to ````www/webroot```` so create that folder and place files in there and it all should work.

Edit ````docker-compose.yml```` and change ````MYSQL_DATABASE: your_database_name```` to the name of your database

Put your initial database dump into db-dumps (.sql files only) - these will automatically be imported into the MySQL database name you added above on provisioning

Then as root:

    vagrant up

**Get a coffee - this will take a while.**

When it has pulled everything down your site will be available at http://192.168.33.10 by default (You can change this in Vagrantfile)

#Troubleshooting

I have occasionally got: 
    
````
There are errors in the configuration of this machine. Please fix the following errors and try again:

vm:
* The 'docker_compose' provisioner could not be found.
````

When provisioning for the first time - it is supposed to install the plugins as it goes but im not entirely sure it does it properly - just do ````vagrant reload```` if you get this and it should carry on.

Alternatively you can do ```` vagrant plugin install vagrant-docker-compose ```` to install the plugin directly
