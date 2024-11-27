FROM node:gallium AS build 
WORKDIR /app

COPY ./frontend /app
RUN npm install && npm run build


FROM nginx:latest AS prod 
COPY --from=build /app/dist /www/project



CMD [ "nginx", "-g", "daemon off;" ]
