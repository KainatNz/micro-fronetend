# pull official base image
FROM node:14-alpine

# set working directory
WORKDIR /app

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# install app dependencies
RUN apk add --no-cache git
COPY package.json ./
COPY package-lock.json ./
RUN npm ci

# add app
COPY . ./

EXPOSE 3000

# start app
CMD ["npm", "start"]