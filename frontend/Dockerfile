
# stage 1
FROM node:16 as frontend-builder

WORKDIR /frontend
COPY package*.json /frontend/
RUN npm install
COPY . . 

# stage 2
FROM node:16-slim

WORKDIR /frontend
COPY --from=frontend-builder /frontend .

CMD [ "npm", "start" ]