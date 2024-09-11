FROM gradle:8.8-jdk17 AS build
WORKDIR /app
COPY . .
RUN gradle build

FROM openjdk:17
WORKDIR /app
COPY --from=build /app/build/libs/project-0.0.1-SNAPSHOT.jar eureka.jar
ENTRYPOINT ["java", "-jar", "eureka.jar"]
