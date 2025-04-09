# Build stage
FROM node:18-alpine as build

# Set working directory
WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy source files and build the Angular app
COPY . .
RUN npm run build --prod

# Production stage using nginx
FROM nginx:alpine

# Copy the compiled app to nginx public directory
COPY --from=build /app/dist/ /usr/share/nginx/html

# Optional: Use custom nginx config for Angular routing
# COPY nginx.conf /etc/nginx/nginx.conf

# Expose port
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]

