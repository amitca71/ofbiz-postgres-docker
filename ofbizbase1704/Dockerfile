from  ubuntu:20.04

ENV DEBIAN_FRONTEND noninteractive
run   apt-get update 
run apt-get install -y --no-install-recommends  wget  unzip subversion  openjdk-8-jre  openjdk-8-jdk 
run apt-get install -y --no-install-recommends git
run git clone https://gitbox.apache.org/repos/asf/ofbiz-framework.git ofbiz-framework
#COPY entitygroup.xml ofbiz.14.12/specialpurpose/bi/entitydef
#COPY entitymodel.xml ofbiz.14.12/specialpurpose/bi/entitydef
workdir ofbiz-framework
run ./gradlew pullAllPluginsSource
COPY ofbiz-component.xml.catalina /ofbiz-framework/framework/catalina/ofbiz-component.xml
run apt install net-tools
run ./gradlew cleanAll loadAll
run ./gradlew "ofbiz --load-data readers=seed,seed-initial,ext,ext-demo"
cmd ./gradlew "ofbiz  --portoffset $PORT"
