FROM maven:3.8.6-jdk-8 AS builder

WORKDIR /app

RUN git clone https://github.com/kkenan/basic-microservices && \
    cd basic-microservices/spring-boot-app && \
    mvn clean package

FROM openjdk:8-jdk-alpine

WORKDIR /app

COPY --from=builder /app/basic-microservices/spring-boot-app/target/spring-boot-app-1.0-SNAPSHOT.jar app.jar
COPY spring-boot-conf.yml /app/config/spring-boot-conf.yml

EXPOSE 8080

CMD ["java", "-jar", "app.jar", "--spring.config.location=file:/app/config/spring-boot-conf.yml"]
