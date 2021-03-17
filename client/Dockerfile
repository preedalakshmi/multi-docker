FROM node:14.14.0-alpine as builder
WORKDIR "/app"
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build


FROM nginx
EXPOSE 3001
COPY ./ngnix/default.com /etc/ngnix/conf.d/default.conf
COPY --from=builder /app/build /use/share/ngnix/html