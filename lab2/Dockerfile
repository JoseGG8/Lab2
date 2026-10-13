FROM maven:latest AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests
FROM eclipse-temurin:23-jre
WORKDIR /app
# Copia el JAR de la etapa 'build' a la etapa actual
COPY --from=build /app/target/lab2.jar lab2.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","lab2.jar"]