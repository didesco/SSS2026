# Usa l'immagine ufficiale di Node.js
FROM node:20-alpine

WORKDIR /app

# Copia i file di configurazione delle dipendenze
COPY package*.json ./

RUN npm install -g @angular/cli
RUN npm install

# Copia il resto del codice
COPY . .

EXPOSE 4200

# Comando di avvio per Angular
CMD ["npm", "start"]