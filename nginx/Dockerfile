FROM nginx:latest

RUN rm -f /var/log/nginx/access.log && rm -f /var/log/nginx/error.log

RUN curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.14.1-amd64.deb && \
    dpkg -i filebeat-7.14.1-amd64.deb

COPY filebeat.yml /etc/filebeat/filebeat.yml
COPY entrypoint.sh /entrypoint.sh
COPY default.conf /etc/nginx/conf.d/default.conf
RUN chmod +x /entrypoint.sh
ENTRYPOINT [ "/entrypoint.sh" ]
