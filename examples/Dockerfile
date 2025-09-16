FROM registry.access.redhat.com/ubi9/nginx-120

ENV NGINX_VERSION=1.20

# Add application sources
#ADD nginx-container/examples/$NGINX_VERSION/test-app/nginx.conf "${NGINX_CONF_PATH}"
#ADD nginx-container/examples/$NGINX_VERSION/test-app/nginx-default-cfg/*.conf "${NGINX_DEFAULT_CONF_PATH}" /opt/app-root/etc/nginx.default.d
#ADD nginx-container/examples/$NGINX_VERSION/test-app/nginx-cfg/*.conf "${NGINX_CONFIGURATION_PATH}"
#ADD nginx-container/examples/$NGINX_VERSION/test-app/*.html ./

ADD $NGINX_VERSION/test-app/nginx.conf /etc/nginx/nginx.conf
ADD $NGINX_VERSION/test-app/nginx-default-cfg/*.conf /etc/nginx.default.d/
ADD $NGINX_VERSION/test-app/nginx-cfg/*.conf /etc/nginx/conf.d/
ADD $NGINX_VERSION/test-app/*.html ./

RUN chgrp -R root /var/cache/nginx /var/run /var/log/nginx && \
    chmod -R 770 /var/cache/nginx /var/run /var/log/nginx

EXPOSE 8080
# Run script uses standard ways to run the application
CMD nginx -g "daemon off;"
