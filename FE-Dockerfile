FROM node:18

WORKDIR /app

# Copy package files
COPY frontend/package*.json ./

RUN npm install

# Copy the rest of the Angular project
COPY . .

EXPOSE 4200

CMD ["npm", "run", "start:docker"]
