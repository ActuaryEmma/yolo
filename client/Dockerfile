FROM node:19.2-slim

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

# RUN npm run build

RUN npm install -g serve

EXPOSE 3000

CMD [ "serve", "-s", "build", "-l", "3000" ]

# FROM nginx:1.23.1-alpine
# EXPOSE 5000
# COPY ./docker/nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf
# COPY --from=build /app/dist /share/nginx/html




