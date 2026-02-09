FROM python:3.13-slim

MAINTAINER Ahmed Souai

# Installer dépendances système
RUN apt update -y && apt install -y \
    python3-dev \
    build-essential \
    libsasl2-dev \
    libldap2-dev \
    libssl-dev \
    gcc \
    make \
    && rm -rf /var/lib/apt/lists/*


# Copier code source et requirements
COPY student_age.py /student_age.py
COPY requirements.txt /requirements.txt

# Installer packages Python
RUN pip3 install -r /requirements.txt

# Créer un volume pour les données persistantes
VOLUME ["/data"]

# Exposer le port
EXPOSE 5000

# Commande de démarrage
CMD ["python3", "/student_age.py"]
