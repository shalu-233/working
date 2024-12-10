#base image
FROM python:alpine3.21

#metadata for dockerfile
LABEL author="Shalaka" organization="lt"

COPY . /app

#working directory to run application
WORKDIR /app/SimpleFastAPI

#downloading necessary dependancies and requirements
RUN chown -R nobody:nobody /app/SimpleFastAPI && \
    pip3 install fastapi uvicorn[standard]

#Defining user 
USER nobody

#exposing required port to run application
EXPOSE 8000

#defining command to run the application
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]



