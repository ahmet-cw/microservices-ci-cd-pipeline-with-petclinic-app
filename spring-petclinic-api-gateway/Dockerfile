FROM openjdk:11-jre
ARG EXPOSE_PORT=8080
ARG DOCKERIZE_VERSION=v0.6.1
ENV SPRING_PROFILES_ACTIVE docker
ADD https://github.com/jwilder/dockerize/releases/download/${DOCKERIZE_VERSION}/dockerize-alpine-linux-amd64-${DOCKERIZE_VERSION}.tar.gz dockerize.tar.gz
RUN tar xzf dockerize.tar.gz && chmod +x dockerize
ADD ./target/*.jar /app.jar
EXPOSE ${EXPOSE_PORT}
ENTRYPOINT [ "java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar" ]

