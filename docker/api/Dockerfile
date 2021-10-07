FROM node:14 as development

WORKDIR /app

COPY package.json package-lock.json prisma ./

RUN npm ci --ignore-scripts --prefer-offline --silent --no-progress --no-audit

COPY . .


FROM node:14-alpine as production
WORKDIR /app
COPY ./dist/apps/server .
ENV PORT=5000
EXPOSE ${PORT}
RUN npm install --production
RUN npm install reflect-metadata tslib rxjs @nestjs/platform-express
CMD node ./main.js