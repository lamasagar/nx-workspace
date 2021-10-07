FROM node:14 as development
# RUN apk add --no-cache git gcc g++ python

WORKDIR /app

COPY package.json package-lock.json prisma ./

RUN npm ci --ignore-scripts --prefer-offline --silent --no-progress --no-audit
# RUN npx prisma generate

COPY . .
