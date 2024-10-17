FROM nginx:1.26.2-alpine3.20

RUN apk add --no-cache apache2-utils
COPY nginx-default.conf /etc/nginx/conf.d/default.conf
RUN --mount=type=secret,id=BASIC_PASSWORD \
    cat /run/secrets/BASIC_PASSWORD | \
    htpasswd -ic /etc/nginx/htpasswd user
