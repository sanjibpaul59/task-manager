FROM node:20-slim 

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . /app

EXPOSE 5173/tcp

CMD ["npm", "run", "dev"]