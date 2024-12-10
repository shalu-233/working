#base image
FROM python:alpine3.21

#metadata for dockerfile
LABEL author="Shalaka" organization="lt"

ENV Database_URL=postgresql://user:password@localhost:5432/libary

COPY . /app

#working directory to run application
WORKDIR /app/SimpleLibrary

#downloading necessary dependancies and requirements
RUN chown -R nobody:nobody /app/SimpleLibrary && \
    pip3 install fastapi uvicorn[standard]

#Defining user
USER nobody

#exposing required port to run application
EXPOSE 8000

#defining command to run the application
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]