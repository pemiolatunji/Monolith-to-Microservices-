# Create node version 
FROM beevelop/ionic:latest AS ionic

# Create working directory 
WORKDIR /usr/src/app

# Install app dependencies 
COPY package.json ./
COPY package-lock.json ./
RUN npm ci

# Bundle the application 
COPY . .
RUN ionic build

## Run
FROM nginx:alpine

# Copy www /usr/share/nginx/html
COPY --from=ionic /usr/src/app/www /usr/share/nginx/html
