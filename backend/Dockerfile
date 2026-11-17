# Usa un'immagine ufficiale di Python
FROM python:3.11-slim

# Imposta la cartella di lavoro dentro il container
WORKDIR /app

# Copia e installa le dipendenze
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copia il codice sorgente
COPY . .

# Esporta la porta su cui gira Uvicorn
EXPOSE 8000

# Comando per avviare il backend
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]