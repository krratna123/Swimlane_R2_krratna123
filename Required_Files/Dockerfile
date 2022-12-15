FROM node:14

MAINTAINER krratna123
WORKDIR /app
COPY package.json ./
RUN npm install
RUN npm audit fix --force
COPY . .

EXPOSE 3000

CMD ["node", "server.js"]
