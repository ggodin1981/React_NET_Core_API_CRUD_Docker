# Use the official Node.js base image
FROM node:18

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the React app
ARG REACT_APP_API_URL
ENV REACT_APP_API_URL=$REACT_APP_API_URL
RUN npm run build

# Install serve globally to serve the build folder
RUN npm install -g serve

# Expose the port the app runs on
EXPOSE 3000

# Start the React app
CMD ["serve", "-s", "build"]
