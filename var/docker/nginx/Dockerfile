FROM alpine:latest

RUN apk add --update --n-cache nginx

COPY nginx.conf /etc/nginx/
COPY symfony.conf /etc/nginx/conf.d/

RUN adduser -D -g '' -G www-data www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443