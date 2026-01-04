FROM node:18-alpine AS builder
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install

FROM node:18-alpine AS final
WORKDIR /app
COPY --from=builder ./node_modules ./node_modules
COPY server.js ./
EXPOSE 3000
CMD ["node", "server.js"]