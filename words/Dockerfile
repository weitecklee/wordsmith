FROM ubuntu
RUN apt-get update
RUN apt-get install maven -y
WORKDIR /app
COPY pom.xml .
RUN mvn verify
COPY . .
RUN mvn verify

FROM alpine
RUN apk add openjdk8-jre
COPY --from=0 /app/target /app/target

WORKDIR /app/target
# CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]
CMD exec java -Xmx8m -Xms8m -jar words.jar