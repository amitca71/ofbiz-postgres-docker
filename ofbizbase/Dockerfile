from  ubuntu:14.04

#copy sources.list.trusty  /etc/apt/sources.list
ENV DEBIAN_FRONTEND noninteractive
run   apt-get update && \
      apt-get install -y --no-install-recommends  wget  unzip subversion  openjdk-7-jre  openjdk-7-jdk  && \
      svn co http://svn.apache.org/repos/asf/ofbiz/branches/release14.12 ofbiz.14.12

workdir ofbiz.14.12

cmd   ./ant load-seed && \
      ./ant load-admin-user-login -DuserLoginId=admin && \
      ./ant start
