# Step 1: Build the Vue app
FROM node:16 AS build-stage

# Set working directory inside the container
WORKDIR /app

# Copy package.json and yarn.lock
COPY package.json yarn.lock ./

# Install dependencies using Yarn
RUN yarn install

# Copy the rest of the application source code
COPY . .

# Build the app for production
RUN yarn build

# Step 2: Serve the app using Nginx
FROM nginx:alpine AS production-stage

# Copy the built files from the previous stage
COPY --from=build-stage /app/dist /usr/share/nginx/html

# Copy Nginx configuration (optional, if you need custom settings)
# COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
