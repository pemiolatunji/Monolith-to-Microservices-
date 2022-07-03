# Create node version to be used 
FROM node:12

# Create app directory 
WORKDIR /usr/src/app

# Copy dependencies
COPY package.json ./
COPY package-lock.json ./
RUN npm ci

# Bundle the app
COPY . .
EXPOSE 8080
CMD ["npm", "run", "prod"]
 
