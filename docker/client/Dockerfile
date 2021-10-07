FROM mhart/alpine-node:14 as base
# RUN echo "https://mirror.csclub.uwaterloo.ca/alpine/v3.9/main" > /etc/apk/repositories
RUN apk add --no-cache git gcc g++ python

WORKDIR /var/www/globaly

COPY ./ ./

RUN npm ci --ignore-scripts --prefer-offline --silent --no-progress --no-audit
