# Select a base image
FROM  node:20-alpine3.17

# Create a directory  and go to directory test
WORKDIR /app

# Copy the package.json file to my current directory for install necessary dependence  
COPY package.json package-lock.json ./

# Install the dependence
RUN npm install

# Copy other file to my current directory
COPY . .

# Open the port for express server
EXPOSE 5000

# Run express rum in foreground test
CMD ["npm", "start"]