# Helidon Quickstart MP Example with JAX-B

This example implements a simple Hello World REST service using MicroProfile.

It started with the Helidon Quickstart and added a POST endpoint that returns XML

## Build and run

With JDK8+
```bash
mvn package
java -jar target/helidon-quickstart-mp.jar
```

## Exercise the application

```
curl -X GET http://localhost:8080/greet
{"message":"Hello World!"}

curl -X GET http://localhost:8080/greet/Joe
{"message":"Hello Joe!"}

curl -X PUT -H "Content-Type: application/json" -d '{"greeting" : "Hola"}' http://localhost:8080/greet/greeting

curl -X GET http://localhost:8080/greet/Jose
{"message":"Hola Jose!"}

curl -X POST -H "Content-Type: application/json" -d '{"greeting" : "Hi"}' http://localhost:8080/greet/postit
<?xml version="1.0" encoding="UTF-8" standalone="yes"?><product><id>1234</id><name>Hi</name><description>Just a Hello</description><price>0</price></product>
```
