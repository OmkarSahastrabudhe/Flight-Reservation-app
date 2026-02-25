FROM node:22-alpine AS build
WORKDIR /app

COPY . .

RUN npm install && npm run build

FROM httpd

COPY --from=build /app/dist/  htdocs/
CMD [ "httpd", "-D", "FOREGROUND" ]