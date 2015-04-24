# MySQL Container #

FROM `fedora:latest`

This service/io boots up mysql against a shared data container.

## Commands ##

### Bootstrap ###
This command will build the mysql container and create/override the data volume container ¡THIS WILL UNREVERSIBLE DELETE SQL DATA!
`./bootstrap`

### Run ###
This command will run the mysql container, binding to the default mysql port and any other ports exposed in the image.
`./run`

### Stop ###
This command will stop the mysql container.
`/stop`

## Docker ##
`docker ps` to view running containers
