# select a base image 
FROM node:20-alpine3.17

# create a directory for the app and go to the directory
WORKDIR /app

# copy the package.json and package-lock.json files to the app directory to install necessary dependencies
COPY package.json package-lock.json ./

# install the dependencies
RUN npm install

# copy the rest of the app files to the app directory
COPY . .

# open the port 5000 for the server
EXPOSE 5000

# run express server on port 5000
CMD ["npm", "start"]

# end of Dockerfile