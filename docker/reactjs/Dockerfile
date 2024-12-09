FROM node:18 AS build


RUN git clone https://github.com/aditya-sridhar/simple-reactjs-app.git && \
    cd simple-reactjs-app && \
    npm install -y


FROM  node:18-alpine

COPY --from=build  simple-reactjs-app   /tmp/

# Set the working directory for subsequent commands
WORKDIR /tmp/simple-reactjs-app

RUN chown -R node /tmp/simple-reactjs-app


USER node

EXPOSE 3000

ENTRYPOINT ["npm" , "run"]

CMD ["start"]