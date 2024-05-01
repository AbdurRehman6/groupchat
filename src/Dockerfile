FROM maven:2.5.3-openjdk-16 AS build
COPY . .
RUN mvn clean package-DskipTests

FROM openjdk:17.0.1-jdk-slim
COPY --from=build /target/chatroomapp-0.0.1-SNAPSHOT.jar chatroomapp.jar
EXPOSE 4000
ENTRYPOINT [ "java","-jar","demo.jar" ]