#Crossbar Router
This is a simple docker container that will initialize a crossbar router with a static website running on it.  It can
be run as follows

##Create Router
To create a router, do the following

    docker run -p 8080:8080 thehq/crossbar

You should be able to go to

    http://<ip_address>:8080
    
And you will see a web page that just says

    Application Router
    
The default realm is "realm1" and there is no authentication.

##Changing Default Version
You can change the default version by specifying the following at the docker command line

    docker run -e "CROSSBAR_VERSION=<version>" -p 8080:8080 thehq/crossbar
    
##Changing Config Information
You can mount a directory with configuration files as follows

    docker run -p 8080:8080 -v <shared directory>:/.crossbar thehq/crossbar

or you can specify trailing crossbar standard command line options

    docker run -p 8080:8080 -v thehq/crossbar --cbdir <directory>

Please consult the "crossbar.io" and "docker" documentation for more details

##Changing Website
The static website is being served out of the folder "/www" so it can be overridden by

    docker run -p 8080:8080 -v <shared directory>:/www thehq/crossbar
    
#License
MIT
