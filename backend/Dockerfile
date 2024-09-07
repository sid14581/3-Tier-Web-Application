# stage 1
FROM node:16 as backend-builder

WORKDIR /backend
COPY package*.json /backend/
RUN npm install
COPY . . 

# stage 2
FROM node:16-slim

WORKDIR /backend
COPY --from=backend-builder /backend /backend/
EXPOSE 3500

CMD [ "node", "index.js" ]