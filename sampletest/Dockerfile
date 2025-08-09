# 🧱 Stage 1: Build the JAR
FROM maven:3.9.6-eclipse-temurin-17 AS builder
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# 🚀 Stage 2: Run the JAR
FROM gcr.io/distroless/java17-debian11
WORKDIR /app
COPY --from=builder /app/target/*.jar app.jar
CMD ["app.jar"]
