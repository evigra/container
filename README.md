# CONTAINER

This repository contains the template to generate the containers

------------------

## CONFIGURATION 



sudo chown $(whoami):$(whoami) /var/run/docker.sock

# Create container
docker run -v ~/docker/container/addons:/mnt/extra-addons -p 8016:8069 -p 8116:8116 --name odoo_16 --link db:db -t odoo:16.0

# Install module gpsmap
docker exec -ti odoo_16 bash -c "/usr/bin/odoo -p 8116 -i gpsmap -d odoo_16 --db_host db --db_port 5432 --db_user odoo --db_password odoo --without-demo all"
