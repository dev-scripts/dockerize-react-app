# Stage 0 :  "build-stage", based on Node.js, to build and compile the frontend
FROM node:16.3.0-alpine as build-stage
# set working directory
WORKDIR /app/


# install app dependencies
COPY package.json /
COPY package-lock.json /
RUN npm install --silent

COPY . .

RUN npm run build

# Stage 1 : 
FROM nginx:1.22-alpine

# Copy built assets from `build-stage` image
COPY --from=build-stage /app/build/ /usr/share/nginx/html

COPY docker/nginx/nginx.conf /etc/nginx/conf.d/default.conf

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
