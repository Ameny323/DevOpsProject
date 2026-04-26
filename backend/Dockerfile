FROM ameni221/mon-springboot:latest

# Install Java 17 (OpenJDK)
RUN apk update && apk add openjdk17

WORKDIR /app

COPY target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]

