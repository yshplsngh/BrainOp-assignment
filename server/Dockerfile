FROM node:22

WORKDIR /usr/src/app

COPY package*.json  ./
COPY tsconfig.json  ./

RUN npm install

COPY prisma ./prisma

RUN npx prisma generate

COPY . .

RUN npm run build

EXPOSE 8000

CMD ["sh", "-c", "npx prisma migrate dev --name init && npm start"]