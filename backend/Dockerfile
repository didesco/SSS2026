# Usa un'immagine ufficiale di Python
FROM python:3.11-slim

# Imposta la cartella di lavoro dentro il container
WORKDIR /app

# Installa git per clonare il repository
RUN apt-get update && apt-get install -y --no-install-recommends git \
    && rm -rf /var/lib/apt/lists/*

# Clona il repository e copia i file del backend in /app
RUN git clone https://github.com/didesco/SSS2026.git /tmp/repo \
    && cp -r /tmp/repo/backend/* /app/ \
    && rm -rf /tmp/repo

# Installa le dipendenze
RUN pip install --no-cache-dir -r requirements.txt

# Esporta la porta su cui gira Uvicorn
EXPOSE 8000

# Comando per avviare il backend
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]