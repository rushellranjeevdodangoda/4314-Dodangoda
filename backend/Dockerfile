# Use an official Node.js runtime as a parent image
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install backend dependencies
RUN npm install

# Copy the rest of the backend code to the working directory
COPY . .

# Expose the port on which your backend server will run (change it if your server runs on a different port)
EXPOSE 3000

# Command to run your backend server
CMD ["npm", "start"]
