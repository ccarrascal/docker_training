##
## Dockerfile for training:httpd, kamilbaran/nobleprog_training:httpd
##

FROM alpine:3.9

RUN apk add apache2 php7-apache2 php7-mongodb --update-cache --no-cache            

RUN ln -sf /dev/stdout /var/log/apache2/access.log && \
    ln -sf /dev/stderr /var/log/apache2/error.log && \
    mkdir -p /run/apache2/

EXPOSE 80
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

COPY ["html/", "/var/www/localhost/htdocs/"]
ENV MONGO_CS="mongodb://localhost:27017"

# Run it with:
## docker network create training
## docker run -d -p 90:80 --name httpd --network training --env MONGO_CS="mongodb://mongo:27017" training:httpd
## docker run -d -p 90:80 -v /Users/charles/projects/DockerTraining/data/html:/var/www/localhost/htdocs --name httpd --network training --env MONGO_CS="mongodb://mongo:27017" training:httpd


## Connect to it:
## docker exec -it httpd /bin/sh