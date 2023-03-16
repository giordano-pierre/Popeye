# Stage 1 - Build the worker
FROM maven:3.8.4-jdk-11-slim AS builder
WORKDIR /app
COPY . /app
RUN mvn dependency:resolve && mvn package

# Stage 2 - Run the worker
FROM openjdk:11-jre-slim
WORKDIR /app
COPY --from=builder /app/target/worker-jar-with-dependencies.jar /app/
CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
