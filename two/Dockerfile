FROM node:14-buster-slim as build

WORKDIR /app

COPY . .

RUN npm ci --silent
RUN npm run build

FROM nginx:1.23.3-alpine

COPY /nginx.conf /etc/nginx/nginx.conf
COPY --from=build /app/build /usr/share/nginx/html



