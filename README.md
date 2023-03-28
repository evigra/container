# CONTAINER

This repository contains the template to generate the containers

------------------

## CONFIGURATION 

sudo chown $(whoami):$(whoami) /var/run/docker.sock
docker-compose up
docker-compose restart

docker exec -tiu root instance_web_1 bash
cp /usr/bin/odoo /usr/bin/odoo_server

docker exec -ti container_web_1 bash -c "/usr/bin/odoo -p 8013 -u gpsmap -d produccion --db_host db --db_port 5432 --db_user odoo --db_password odoo --without-demo all"
docker exec -ti container_web_1 bash -c "/usr/bin/odoo -p 8013 -u gpsmap -d developer  --db_host db --db_port 5432 --db_user odoo --db_password odoo"


