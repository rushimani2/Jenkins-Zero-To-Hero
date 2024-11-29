# You can change this base image to anything else
# But make sure to use the correct version of Java
##FROM adoptopenjdk/openjdk11:alpine-jre

# Simply the artifact path
##ARG artifact=target/spring-boot-web.jar

##WORKDIR /opt/app

##COPY ${artifact} app.jar

# This should not be changed
##ENTRYPOINT ["java","-jar","app.jar"]

FROM ubuntu:latest
WORKDIR /opt/app
COPY pom.xml ./
COPY src ./src
RUN apt-get update && apt install openjdk-17-jdk -y && apt install maven -y
CMD [ "mvn", "spring-boot:run" ]
EXPOSE 8080
