FROM maven:3.8.1-jdk-8 AS builder

WORKDIR /Code

COPY . .

RUN mvn package

FROM openjdk:17-slim

WORKDIR /Code
COPY --from=builder /Code/startApp/target/startApp-1.0-SNAPSHOT.jar Code.jar

CMD ["java", "-jar", "Code.jar"]