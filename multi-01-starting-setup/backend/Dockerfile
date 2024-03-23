FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 8080

# ENV MONGO_INITDB_ROOT_USERNAME=hfshan247
# ENV MONGO_INITDB_ROOT_PASSWORD=Password123

CMD ["npm", "start"]