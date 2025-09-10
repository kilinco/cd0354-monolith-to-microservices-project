### Build
# Use a modern, official Node.js image
FROM node:18-alpine AS ionic

# Set the working directory
WORKDIR /usr/src/app

# Install Ionic and Angular CLI globally
RUN npm install -g @ionic/cli @angular/cli

## Install app dependencies
## A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY package*.json ./
RUN npm ci

## Bundle app source
COPY . .
RUN ionic build

### Run 
FROM nginx:alpine
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html
