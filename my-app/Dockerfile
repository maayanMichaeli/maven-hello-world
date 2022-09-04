FROM ubuntu:latest
RUN useradd -m -p Nopassword javauser
USER javauser

FROM maven:3.8.6-jdk-8 AS build
WORKDIR /home/my-app
COPY src /home/my-app/src
COPY pom.xml /home/my-app
RUN mvn -B clean package

FROM openjdk:8-jre-alpine
WORKDIR /app
COPY --from=build /home/my-app/target/my-app-1.0.0-SNAPSHOT.jar /app.jar
CMD ["/usr/bin/java", "-jar", "/app.jar"]

