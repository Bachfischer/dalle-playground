FROM node:lts-slim

EXPOSE 80

COPY package.json /code/package.json

COPY package-lock.json /code/package-lock.json

WORKDIR /code

COPY . /code

RUN npm install

CMD PORT=80 npm start
