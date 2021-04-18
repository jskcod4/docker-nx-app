FROM node:14.16.1-alpine3.10 as build-step

RUN mkdir -p /app

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . /app

RUN npm run build

FROM nginx:1.19.10-alpine

COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build-step /app/dist/apps/web-frontend /usr/share/nginx/html
