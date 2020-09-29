FROM node:alpine as builder
WORKDIR "/app"
COPY ./package/json ./
RUN npm isntall
COPY . .
RUN npm run build

FROM nginx
EXPOSe 3000
COPY ./nginx.default.conf /etc/nginx/conf.d/default.conf
COPY --from=build /app/build /usr/share/nginx/html