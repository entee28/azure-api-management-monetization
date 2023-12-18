FROM node:18 as base
WORKDIR /usr/app
COPY package*.json ./
RUN npm install
COPY . .

FROM node:18-alpine as production
WORKDIR /usr/app
COPY --from=base /usr/app ./
RUN npm run build
EXPOSE 8000
CMD [ "node", "dist/index.js" ]