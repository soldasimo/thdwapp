FROM java:8-alpine
COPY . /usr/src/hello-dropwizard
WORKDIR /usr/src/hello-dropwizard
CMD ["java", "-jar", "target/hello-dropwizard-1.0-SNAPSHOT.jar", "server", "example.yml"]
