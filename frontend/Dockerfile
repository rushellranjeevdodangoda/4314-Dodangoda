# Use an official Node.js runtime as a parent image
FROM node:14 as build

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install frontend dependencies
RUN npm install

# Copy the rest of the frontend code to the working directory
COPY . .

# Build the frontend application
RUN npm run build

# Stage 2 - Serve the static files
FROM nginx:alpine

# Copy the build output from the previous stage
COPY --from=build /app/build /usr/share/nginx/html

# Expose the port on which the frontend will run (default is 80)
EXPOSE 80

# Command to start the nginx server
CMD ["nginx", "-g", "daemon off;"]
