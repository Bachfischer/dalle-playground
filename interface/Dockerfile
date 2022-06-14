FROM node:lts-slim as build-stage

COPY package.json /code/package.json

COPY package-lock.json /code/package-lock.json

WORKDIR /code

COPY . /code

RUN npm install

RUN npm run build

FROM nginx:latest

EXPOSE 80

COPY --from=build-stage /code/build/ /usr/share/nginx/html

COPY nginx.conf /etc/nginx/conf.d/default.conf