##
## Dockerfile for training:mongo, kamilbaran/nobleprog_training:mongo
##

FROM alpine:3.9

RUN mkdir -p /data/db && \
    addgroup -S -g 27017 mongodb && \
    adduser -S -u 27017 -g mongodb mongodb && \
    chown -R mongodb:mongodb /data

RUN apk add mongodb --update-cache --no-cache

VOLUME ["/data/db/"]
EXPOSE 27017
USER mongodb
ENTRYPOINT ["/usr/bin/mongod", "--dbpath=/data/db"]

# Run it with:
## docker network create training
## docker run -d --name mongo --network training training:mongo --bind_ip_all
## docker run -v mongo-data:/data/db -d --name mongo --network training training:mongo --bind_ip_all