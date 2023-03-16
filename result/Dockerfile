FROM node:12-alpine
WORKDIR /app
COPY . /app
RUN npm install --only=production
ENV NODE_ENV=production
EXPOSE 80
CMD ["node", "server.js"]
