FROM nginx:alpine

# Sovrascrive la configurazione di default di Nginx
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]