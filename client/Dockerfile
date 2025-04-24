# stage-1 & specify the base image 
FROM node:23-alpine3.20 AS builder

# create a directory for the app and go to the directory
WORKDIR /app

# copy the package.json and package-lock.json files to the app directory to install necessary dependencies
COPY package.json package-lock.json ./

# install the dependencies
RUN npm install

# copy the rest of the app files to the app directory
COPY . .

# build the app
RUN npm run build

# stage-2 & specify the base image
FROM nginx:1.25.2-alpine-slim 

# copy the build files from the builder stage to the nginx html directory
COPY --from=builder /app/build /usr/share/nginx/html

# expose the port 80 for the nginx server
EXPOSE 80

# start the nginx server
CMD ["nginx", "-g", "daemon off;"]

# end of Dockerfile


