# server/Dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm ci

COPY . .

# No need to copy .env — docker-compose will inject it at runtime

EXPOSE 5000

CMD ["npm", "start"]
