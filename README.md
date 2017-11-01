# Transmission

Transmission is a fast, easy, and free cross-platform BitTorrent client.

# How to use this image

This container is meant to be as minimal as possible and as such it runs a daemon with dropped privileges, no more no less. It is recommended to run it the container once to create the settings file; which you can then modify outside of a container instance.

    sudo docker run --name transmission -v /path/to/config:/config 
        -v /path/to/downloads:/downloads -v /path/to/watch:/watch 
        -p 9091:9091 -p 51413:51413 -d trezamere/transmission

    http://hostname:9091/transmission/web/

### Setting the Timezone

There are a number of ways to set the timezone in docker if desired; the simplest would be to share the hosts timezone with your container

    sudo docker run -v /etc/localtime:/etc/localtime:ro trezamere/transmission
