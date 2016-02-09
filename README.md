# ofbiz-postgres-docker
This repository is creating ofbiz docker instance and postgresql instance
In order to operate it, need to follow the following steps:
1. create ofbiz network:
  sudo docker network create ofbiz

2. build and boot db image :
   cd <docker_home>/dockerpostdb
   sudo docker-compose build 
   sudo docker-compose up -d

3. build and boot ofbiz image:
   cd <docker_home>/ofbizbase
   sudo docker-compose build
   sudo docker-compose up -d
(be aware that ofbizbase doesnt create admin user database, 
after 1st execusion need to overide the command in composer yml file- usualy will be done on separate layer )


