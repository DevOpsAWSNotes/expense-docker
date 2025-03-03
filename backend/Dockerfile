# FROM node:20
FROM node:20.18.3-alpine3.21
WORKDIR /opt/backend
COPY package.json .
COPY *.js .
RUN npm install
#using docker network
ENV DB_HOST="mysql"
#using local host network
# ENV DB_HOST="localhost" 
CMD ["node", "index.js"]