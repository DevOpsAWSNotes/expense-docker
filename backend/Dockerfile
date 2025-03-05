# FROM node:20
FROM node:20.18.3-alpine3.21 as builder
# RUN addgroup -S expense && adduser -S expense -G expense && \
#     mkdir /opt/backend && \
#     chown -R expense:expense /opt/backend
WORKDIR /opt/backend
# ENV DB_HOST="mysql"
# USER expense    
COPY package.json .
COPY *.js .
RUN npm install
#using docker network
# ENV DB_HOST="mysql"
#using local host network
# ENV DB_HOST="localhost" 
# USER expense
# CMD ["node", "index.js"]


From node:20.18.3-alpine3.21
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/backend && \
    chown -R expense:expense /opt/backend
ENV DB_HOST="mysql"
WORKDIR /opt/backend
USER expense
COPY --from=builder /opt/backend /opt/backend
CMD ["node", "index.js"]