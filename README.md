# ofbiz-postgres-docker
This repository is creating ofbiz docker instance and postgresql instance
In order to operate it, need to follow the following steps:
1. create ofbiz network:
  sudo docker network create ofbiz

2. build ofbizbase1704 :
   cd <docker_home>/ofbizbase1704
   sudo docker-compose build 
   (sudo docker-compose up -d - will boot the server with derby embeded db)

3. in order to use postgres 
   cd <docker_home>/dockerpostdb
   sudo docker-compose build
   sudo docker-compose up -d

ofbizbase - is deprecated, builds old version of ofbiz with derby


