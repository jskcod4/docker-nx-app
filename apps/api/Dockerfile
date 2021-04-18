FROM node:14.16.1-alpine3.10

COPY ["package.json", "package-lock.json", "/usr/src/"]

WORKDIR /usr/src

RUN npm install

COPY [".", "/usr/src/"]

EXPOSE 3000

RUN npx nx build api

CMD ["node", "/usr/src/dist/apps/api/main.js"]
