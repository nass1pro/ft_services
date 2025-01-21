FROM alpine

RUN apk update && \
    apk upgrade && \
    apk add --repository http://dl-3.alpinelinux.org/alpine/edge/testing/ pure-ftpd && \
    apk add openssl curl

RUN adduser -D -h /home/nass nass && \
    echo -e 'pass\npass' | passwd nass && \
    echo -e 'pass\npass' | pure-pw useradd nass -u nass -g nass -d /home/nass

RUN openssl req -x509 -nodes -days 7300 -subj "/C=FR/ST=fr/L=Belgiaque/O=19/CN=nass" \
    -newkey rsa:2048 -keyout /etc/ssl/private/pure-ftpd.pem -out /etc/ssl/private/pure-ftpd.pem

RUN curl 'https://dl.influxdata.com/telegraf/releases/telegraf-1.16.0_linux_i386.tar.gz' > telegraf.tar.gz && \
    tar xvf telegraf.tar.gz && \
    mv 'telegraf-1.16.0' telegraf
COPY telegraf.conf /etc/telegraf/telegraf.conf

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x entrypoint.sh

EXPOSE 21
EXPOSE 21000
EXPOSE 21001
EXPOSE 21002
EXPOSE 21003
EXPOSE 21004
EXPOSE 21005

CMD "/entrypoint.sh"
