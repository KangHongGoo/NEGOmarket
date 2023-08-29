FROM node:18.16.0 as build

ENV REACT_APP_TOP TOP welcome to Korea.
ENV REACT_APP_TEST heehee

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . ./

RUN npm run build

FROM nginx:alpine
#COPY nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80

CMD [ "nginx", "-g", "daemon off;" ]