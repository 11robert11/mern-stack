FROM node:19.7.0
ENV NODE_ENV=development

WORKDIR /app

COPY ["package.json", "package-lock.json*", "./"]

RUN npm install

#COPY . .

CMD [ "npm", "run", "start"]