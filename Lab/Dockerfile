FROM openjdk:17oracle as build

COPY .mvm  .mvn
COPY mvnw .
COPY pom.xml .
COPY src src

RUN ./mvnw -B package

FROM openjdk:17-oracle

COPY --from=build target/app-1.jar .

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app-1.jar"]