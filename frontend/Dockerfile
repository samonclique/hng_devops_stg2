FROM node:20-alpine AS base

WORKDIR /app

RUN apk update \
    && apk add --no-cache libc6-compat curl

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 5173

CMD [ "npm", "run", "dev", "--", "--host" ]