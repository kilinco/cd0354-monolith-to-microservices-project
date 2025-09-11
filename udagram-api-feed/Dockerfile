FROM node:18.17.0-alpine

RUN pwd
RUN ls -la

## Create app directory
WORKDIR /usr/src/app

RUN pwd
RUN ls -la

## Install app dependencies
## A wildcard is used to ensure both package.json AND package-lock.json are copied where available (npm@5+)
COPY package*.json ./
RUN npm ci 

## Bundle app source
COPY . .
EXPOSE 8080
CMD [ "npm", "run", "prod" ]
