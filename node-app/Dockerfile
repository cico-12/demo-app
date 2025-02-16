FROM node:9.9.0

WORKDIR /app

RUN git clone https://github.com/kkenan/basic-microservices && \
    mv basic-microservices/node-app/* . && \
    rm -rf basic-microservices

RUN npm install

EXPOSE 8081

CMD ["node", "index.js"]
