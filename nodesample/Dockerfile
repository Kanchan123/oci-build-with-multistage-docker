FROM node:10 as build
LABEL description="Sample NPM multi build dockerfile"
WORKDIR /src
COPY package*.json .
RUN npm install
COPY . .

FROM node:10-slim
WORKDIR /src
COPY --from=build /src .
EXPOSE 8080
CMD ["node", "index.js"]