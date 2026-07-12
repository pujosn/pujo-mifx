FROM alpine:3.20

RUN apk add --no-cache \
        nginx \
        php82 \
        php82-fpm

COPY nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /run/nginx /var/www/html \
    && chown -R nginx:nginx /var/www/html /var/lib/nginx /var/log/nginx

EXPOSE 80

CMD ["/bin/sh", "-c", "php-fpm82 -F & nginx -g 'daemon off;'"]
