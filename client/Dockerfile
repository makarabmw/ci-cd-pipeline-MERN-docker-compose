# Stage 1 - Build React App
FROM node:latest AS builder

WORKDIR /app

# Copy only package.json and package-lock.json first (to leverage caching)
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app
COPY . .

# Build optimized production files
RUN npm run build

# Stage 2 - Serve React App with Nginx
FROM nginx:1.25.2-alpine-slim

# Copy build output to Nginx's HTML folder
COPY --from=builder /app/build /usr/share/nginx/html

# Expose port
EXPOSE 80

# Run Nginx in foreground
CMD ["nginx", "-g", "daemon off;"]