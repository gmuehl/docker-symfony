FROM alpine:latest

RUN apk add --update --n-cache nginx

COPY nginx.conf /etc/nginx/
COPY symfony.conf /etc/nginx/conf.d/

RUN echo "upstream php-upstream { server php:9001; }" > /etc/nginx/conf.d/upstream.conf

CMD ["nginx"]

EXPOSE 80
EXPOSE 443