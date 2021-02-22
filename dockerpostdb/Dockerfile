FROM ofbizbase1704_ofbiz:latest
COPY entityengine.xml /ofbiz-framework/framework/entity/config/entityengine.xml
run mkdir -p framework/entity/lib/jdbc/
run wget https://jdbc.postgresql.org/download/postgresql-42.2.1.jar
run mv postgresql-42.2.1.jar  framework/entity/lib/jdbc/
run apt-get update
run apt-get -y install postgresql-client
cmd ./gradlew loadAll && ./gradlew "ofbiz --load-data readers=seed,seed-initial,ext,ext-demo" && ./gradlew ofbiz
