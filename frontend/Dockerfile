# Usa l'immagine ufficiale di Node.js
FROM node:20-alpine AS builder

WORKDIR /app

RUN apk add --no-cache git

RUN git clone https://github.com/didesco/SSS2026.git /tmp/repo \
    && cp -r /tmp/repo/frontend/* /app/ \
    && rm -rf /tmp/repo

# Copia i file di configurazione delle dipendenze
COPY package*.json ./

# Installa le dipendenze e compila l'app Angular
RUN npm install

RUN npm run build -- --configuration production

# serve i file statici compilati con Nginx
FROM nginx:alpine

COPY --from=builder /app/dist/SomeBankingFrontend/browser /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]