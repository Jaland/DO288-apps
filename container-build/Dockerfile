# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

EXPOSE 8080

LABEL io.openshift.expose-services="8080:http"

LABEL io.k8s.description="A basic apache http server child image, uses ONBUILD"

RUN sed -i "s/Listen 80/LISTEN 8080/g" /etc/http/conf/httpd.conf

RUN hgrp -R 0 /var/log/httpd /var/run/httpd && \chmod -R g=u /var/log/httpd /var/run/httpd

USER 1001
