FROM httpd:2.4-alpine
RUN apk update; \
    apk upgrade;


ENV APACHE_RUN_USER root
ENV APACHE_RUN_GROUP root
ENV APACHE_LOG_DIR /var/log/apache2


# Copy apache vhost file to proxy php requests to php-fpm container
COPY app.apache.conf /usr/local/apache2/conf/app.apache.conf


# Customize httpd.conf to enable mod_rewrite
RUN sed -i '/LoadModule rewrite_module/s/^#//g' /usr/local/apache2/conf/httpd.conf && \
    sed -i 's#AllowOverride [Nn]one#AllowOverride All#' /usr/local/apache2/conf/httpd.conf; \
    echo "Include /usr/local/apache2/conf/app.apache.conf" >> /usr/local/apache2/conf/httpd.conf;