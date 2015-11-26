# Crossbar Router
This is a simple docker container that will initialize a crossbar router with a static website running on it.  It can
be run as follows

## Create Router
To create a router, do the following

    docker run -p 8080-8081:8080-8081 thehq/crossbar

Port 8080 is for rawsocket
Port 8081 is for websocket

## Changing Default Version
You can change the default version by specifying the following at the docker command line

    docker run -e "CROSSBAR_VERSION=<version>" -p 8080:8080 thehq/crossbar
    
## Changing Config Information
You can mount a directory with configuration files as follows

    docker run -p 8080:8080 -v <shared directory>:/.crossbar thehq/crossbar

or you can specify trailing crossbar standard command line options

    docker run -p 8080:8080 -v thehq/crossbar --cbdir <directory>

Please consult the "crossbar.io" and "docker" documentation for more details

## Changing Website
The static website is being served out of the folder "/www" so it can be overridden by

    docker run -p 8080:8080 -v <shared directory>:/www thehq/crossbar
    
## License
MIT
