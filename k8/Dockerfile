#Runtime base image
FROM eclipse-temurin:21-jre-alpine


#adding metadata about project
LABEL project="testing" stage="final"


COPY . /tmp/

WORKDIR /tmp

#switching the directory at jar path
RUN chown -R nobody:nobody /tmp/spring-petclinic

#user to run application
USER nobody


EXPOSE 8080

#Running the application
CMD ["java", "-jar", "/tmp/spring-petclinic/target/spring-petclinic-3.4.0-SNAPSHOT.jar"]