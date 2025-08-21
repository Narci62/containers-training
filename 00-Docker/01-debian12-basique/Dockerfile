FROM debian:12

#installer les dependances
RUN apt-get update
RUN apt-get install -y python3 python3-pip
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

#repertoire de travail
WORKDIR /app

#on copie le contenu de /app dans notre repertoire de travail /app
COPY /app /app

#on install les dependances
RUN pip3 install --no-cache-dir --break-system-packages -r requirements.txt

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]