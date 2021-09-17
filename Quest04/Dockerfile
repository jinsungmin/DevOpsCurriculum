FROM node:14-alpine

EXPOSE 5000
HEALTHCHECK --interval=30s --timeout=10s CMD wget -qO- "localhost:5000"

WORKDIR /app

COPY ./package.json ./
RUN npm i

COPY ./build/src ./src
COPY ./nginx ./

CMD ["sh", "-c", "node --stack-trace-limit=20 ./src/index.js"]
