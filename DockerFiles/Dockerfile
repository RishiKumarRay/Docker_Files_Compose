FROM maven:ibmjava-alpine AS build
WORKDIR /hello_spring
COPY . .
RUN mvn clean package


FROM eclipse-temurin:11-jre-alpine
COPY  --from=build /hello_spring/target/hello-0.0.1-SNAPSHOT.jar .
EXPOSE 8080
ENTRYPOINT ["java" , "-jar"]
CMD [ "hello-0.0.1-SNAPSHOT.jar" ]

