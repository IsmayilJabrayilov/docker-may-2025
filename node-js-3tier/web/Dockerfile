FROM node:18  AS builder 

WORKDIR /usr/src/app

COPY package.json . 

RUN npm install 

COPY . . 

# Next stage
FROM node:18-slim

WORKDIR /usr/src/app

COPY --from=builder /usr/src/app .

ENV PORT=3000 \
    API_HOST=http://34.55.213.47:3001 

EXPOSE 3000

CMD ["npm","start"]


