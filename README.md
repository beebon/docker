# docker description
base centos and integrate with nginx/tomcat/openjdk/redis/mariadb

# build image
docker build -t myserver:v1 .

# run containner
docker run --privileged --rm -dit \
-p80:80 -p8080:8080 -p6379:6379 -p3307:3306 \
-v ~/data/nginx:/usr/share/nginx \
-v ~/data/tomcat:/usr/share/tomcat/webapps \
-v ~/data/mysql:/var/lib/mysql \
-v ~/data/redis:/var/lib/redis \
--name myserver myserver:v1 init 

# connect to containner
docker exec -it myserver bash

# start service in containner
servcie nginx start
service tomcat start
service mariadb start
service redis start


