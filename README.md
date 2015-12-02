GeoReferencer
===========

## Development setup
--------------

The development setup requires only docker & docker compose > 1.7 present on the system.

It sets up 3 docker images - a webserver (with Gdal tools cli compiled & installed), an asset builder and a geoserver.

Steps to setup a development environment:

1. git clone git@github.com:picturae/GeoReferencer.git ./geo
2. cd ./geo
3. docker-compose up
4. Edit your hosts file to point georeferencer.dev, georeferencer-api.dev & geoserver.dev to the IP of your docker host.

Dependencies are automatically fetched & installed. If you want to add a new one, simply remove the node_modules folder
and up the containers.
Also you need to add <script type="text/javascript" src="//maps.google.com/maps/api/js?v=3&sensor=false"></script> in
your html.

*NB:* If you get a permission error regarding node_modules and sass_cache. Just remove the folders manually and run
docker-compose up again if the containers are not launching.

## Bonus

Get familiar with the docker commands.

docker-compose rm, docker-compose stop, docker-compose build & docker-compose up are your friends!

## Configuration
--------------

It is possible to alter the configuration on the tool to allow it to run in your own environment.

By making changes in app/app.cfg you are able to alter the parameters used to configure where the hosts are running and
where the geoserver can be found. Changes made to this file and the nginx site configuration files in
resources/gdal/sites-enabled will allow you to either change the ports used, use existing installs of the tools or allow
you to configure the system to run using different hostnames.
