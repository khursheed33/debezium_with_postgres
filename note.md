
Connect with Postgres:

curl -i -X POST -H "Accept: application/json" -H "Content-Type: application/json" 127.0.0.1:8083/connectors/ --data "@debezium.json"


docker run --tty \
--network postgres_debezium_cdc_default \
confluentinc/cp_kafkacat \
kafkacat - b kafka:9092 -C \
-s key=s -s value=avro \
-r http://schema-registry:8081 \
-t postgres.public.student

OR::::

docker run --tty --network postgres_deb_default confluentinc/cp-kafkacat kafkacat -b kafka:9092 -C -s key=s -s value=avro -r http://schema-registry:8081 -t postgres.public.student



Postgres DB Queries:::::::::::::;;;

psql -U docker -d actionai -w

CREATE TABLE student (id int PRIMARY KEY, name varchar);

INSERT INTO student (1,"Khursheed");

SELECT * FROM student;