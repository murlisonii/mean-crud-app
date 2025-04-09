# Use official Node.js image
FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# ✅ Change exposed port to 8080 to match server.js
EXPOSE 8080

CMD ["node", "server.js"]


