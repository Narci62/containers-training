#On part d’un système Debian 12 minimal comme fondation
FROM debian:12

#repertoire de travail
WORKDIR /app

#on copie le contenu de /app dans notre repertoire de travail /app
COPY /app /app

#installer les dependances 
RUN apt-get update && \
    apt-get install -y --no-install-recommends python3 python3-pip && \
    #et nottoyer le cache apt après l'installatin des paquets
    apt-get clean && rm -rf /var/lib/apt/lists/* && \
    #on install les dependances
    pip3 install --no-cache-dir --break-system-packages -r requirements.txt

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]