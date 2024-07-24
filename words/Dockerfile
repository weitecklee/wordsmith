FROM ubuntu
RUN apt-get update
RUN apt-get install maven -y
WORKDIR /app
COPY pom.xml .
RUN mvn verify
COPY . .
RUN mvn verify

FROM ubuntu
RUN apt-get update
RUN apt-get install openjdk-8-jre -y
COPY --from=0 /app/target /app/target

WORKDIR /app/target
# CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]
CMD exec java -Xmx8m -Xms8m -jar words.jar