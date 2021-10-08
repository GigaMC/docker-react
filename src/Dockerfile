FROM node:alpine as builder
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN nmp run build

FROM nginx
EXPOSE 443
COPY --from=builder /app/build /usr/share/nginx/html