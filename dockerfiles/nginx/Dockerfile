ARG phpApp=phpapp
FROM $phpApp

FROM nginx:1.13-alpine

COPY --from=0 /app/public/ /var/www/project/public/
