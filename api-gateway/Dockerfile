FROM maven:3.8.7 as build
COPY . .
RUN mvn package -DskipTests
# Build stage
FROM openjdk:19-jdk-slim
# Copy the packaged Spring Boot application JAR file into the container
COPY --from=build target/api-gateway-0.0.1-SNAPSHOT.jar api-gateway-0.0.1-SNAPSHOT.jar
# Set the command to run your Spring Boot application when the container starts
CMD ["java", "-jar", "api-gateway-0.0.1-SNAPSHOT.jar"]