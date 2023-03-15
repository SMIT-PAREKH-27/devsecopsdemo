# FROM node:14 AS build
# WORKDIR /web
# COPY tsconfig.json ./
# RUN npm install
# COPY . ./
# RUN npm run build
# FROM nginx:1.21.0-alpine
# COPY --from=build /app/build /usr/share/nginx/html
# EXPOSE 80
# CMD ["nginx", "-g", "daemon off;"]
#======================

# Use an official Node.js runtime as a parent image
FROM node:14-alpine
# Set the working directory to /app
WORKDIR src/web
# Copy the package.json and package-lock.json files to the container
COPY package*.json ./
# Install dependencies
RUN npm install
# Copy the rest of the application code to the container
COPY . .
# Build the React app
RUN npm run build
# Set the environment variable to serve the app on port 80
ENV PORT=80
# Expose the port used by the app
EXPOSE 80
# Start the app
CMD ["npm", "start"]