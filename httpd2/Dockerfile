FROM ubuntu:18.04

RUN apt-get update && \
	apt-get install --no-install-recommends -y apache2 && \
	apt-get clean && \
	rm -fr /var/lib/apt/lists/*

#ENV APACHE_LOCK_DIR=/var/lock/apach2 \
	#APACHE_PID_FILE=/var/run/apache2/apache2.pid \
	#APACHE_RUN_USER=www-data \
	#APACHE_RUN_GROUP=www-data \
	#APACHE_LOG_DIR=/var/log/apache2 \
	#APACHE_RUN_DIR=/tmp

CMD apachectl -D FOREGROUND


# Build image:
# docker image build -t training:httpd2 .

# Run it with bash interactive
# docker container run --rm -it --name httpd2 -p 90:80 training:httpd2 bash

# Run it properly detached
# docker run -rm -d -p 90:80 --name httpd2 training:httpd2



