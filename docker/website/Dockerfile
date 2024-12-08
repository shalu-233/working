FROM nginx:1.27

#Copying file from local to container
COPY --chown=nginx:nginx --chmod=755 finexo-html /usr/share/nginx/html/

# Set the working directory
WORKDIR /usr/share/nginx/html/

#changing user
USER nginx

# Expose port 80
EXPOSE 80




++++++++++++


(Correct one)

FROM eclipse-temurin:21-jdk-alpine AS build

LABEL project="testing" stage="first"


RUN apk update && \
    apk add --no-cache git shadow && \
    git clone https://github.com/spring-projects/spring-petclinic.git && \
    cd spring-petclinic/ && \
    ./mvnw package


#Runtime base image
FROM eclipse-temurin:21-jre-alpine

#adding metadata about project
LABEL project="testing" stage="final"

#copying folder from stage first to final
COPY --from=build spring-petclinic /tmp/spring-petclinic

WORKDIR /tmp

#switching the directory at jar path
RUN chown -R nobody:nobody /tmp/spring-petclinic

#user to run application
USER nobody

#Running the application
CMD ["java", "-jar", "/tmp/spring-petclinic/target/spring-petclinic-3.4.0-SNAPSHOT.jar"]