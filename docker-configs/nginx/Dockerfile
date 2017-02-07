FROM nginx:1.10.3

COPY default.conf /etc/nginx/conf.d/default.conf

RUN usermod -u 1000 www-data

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]

