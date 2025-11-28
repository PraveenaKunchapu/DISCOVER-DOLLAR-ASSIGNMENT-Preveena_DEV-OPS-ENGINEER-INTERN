# Use official Node.js image
FROM node:18

# Set work directory inside container
WORKDIR /usr/src/app

# Copy package.json & lock file from the backend folder
COPY backend/package*.json ./

# Install dependencies
RUN npm install

# Copy backend source code into the container
COPY backend/ .

# Expose backend port
EXPOSE 8080

# Start the node server
CMD ["node", "server.js"]
