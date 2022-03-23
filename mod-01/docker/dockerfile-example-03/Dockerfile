FROM ubuntu:20.04

ENV TZ=Europe/London
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update >/dev/null && apt-get install -y apache2 git && apt-get clean

RUN cd /tmp && git clone https://github.com/cloudacademy/static-website-example && \
    mv static-website-example /var/www/html

EXPOSE 80

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
