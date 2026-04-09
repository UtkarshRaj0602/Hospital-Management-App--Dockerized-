####################Hospital-Management-App-Dockerfile####################

####################STAGE - 1 - Builder/Build Stage####################
FROM node:18 AS builder

WORKDIR /app

COPY *.json ./

RUN npm install --omit=dev

COPY . .

####################STAGE - 2 - Runner/Run Stage####################
FROM node:18-alpine

WORKDIR /app

COPY --from=builder /app ./

EXPOSE 3000

CMD ["node", "app.js"]
