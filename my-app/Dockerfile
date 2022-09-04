FROM ubuntu:latest

FROM openjdk:8-jre-alpine
USER ubuntu
COPY target/my-app-1.0.0-SNAPSHOT.jar /app.jar
CMD ["/usr/bin/java", "-jar", "/app.jar"]

