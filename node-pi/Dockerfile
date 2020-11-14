FROM arm32v7/node AS builder
WORKDIR /app
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build
FROM arm32v7/node
WORKDIR /app
COPY --from=builder /app ./
CMD ["npm", "run", "start:prod"]