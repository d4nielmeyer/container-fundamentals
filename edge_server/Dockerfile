# use a minimal base image that already includes NGINX, such as the official NGINX Alpine image.
FROM nginx:stable-alpine

LABEL org.opencontainers.image.authors="danielmeyer92@magenta.de"
LABEL org.opencontainers.image.source="https://github.com/d4nielmeyer/container-fundamentals"
LABEL org.opencontainers.image.description="Containter Fundamentals - Static Website Image"
LABEL org.opencontainers.image.licenses=APACHE2
 
# # No need for apt update or install, nginx is already included in this image.
# RUN apt update --no-cache && apt install nginx -y

# When switching to the nginx:stable-alpine image, the NGINX server is already set up and configured to use different paths
COPY config/nginx.conf /etc/nginx/conf.d/default.conf
COPY web_content/ /usr/share/nginx/html

COPY config/nginx.conf /etc/nginx/
COPY web_content/ /var/www
EXPOSE 80

# CMD is already ["nginx", "-g", "daemon off;"] in nginx:stable-alpine image, so no need to repeat it.
# CMD ["nginx", "-g", "daemon off;"]
