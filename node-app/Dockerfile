FROM node:9.9.0

WORKDIR /app

RUN git clone https://github.com/kkenan/basic-microservices && \
    mv basic-microservices/node-app/* . && \
    rm -rf basic-microservices

RUN npm install

EXPOSE 8081

CMD ["node", "index.js"]



# Alternative way
# Clone basic-microservices repository locally and go inside the basic-microservices/node-app/ directory
# Create Dockerfile and paste the configuration bellow, than remove the comment tag from the start of each line and comment/delete configuration above

# FROM node:9.9.0

# WORKDIR /app

# COPY package*.json ./

# RUN npm install

# COPY . .

# EXPOSE 8081

# CMD ["node", "index.js"]
