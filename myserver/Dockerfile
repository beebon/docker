#a container base in centos with jdk18/tomcat7/redis/mariadb/nginx
#base image
FROM centos

#install bash service
RUN yum update -y
RUN yum install initscripts -y

#install nginx
RUN rpm -Uvh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
RUN yum install nginx java-1.8.0-openjdk.x86_64 -y

#install redis
RUN yum install -y http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
RUN yum install -y redis

#install openjdk1.8
RUN yum install java-1.8.0-openjdk.x86_64 -y

#install tomcat
RUN yum install tomcat -y

#install mariadb
RUN yum install -y mariadb mariadb-server

EXPOSE 80
EXPOSE 6379
EXPOSE 8080
