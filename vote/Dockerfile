# 1. Utiliser une image Python
FROM python:3.9

# 2. Définir le répertoire de travail
WORKDIR /app

# 3. Copier les fichiers nécessaires
COPY app.py requirements.txt /app/
COPY templates/ /app/templates/
COPY static /app/static


# 4. Installer les dépendances
RUN pip install -r requirements.txt

# 5. Exposer le port utilisé par Flask
EXPOSE 8080

# 6. Lancer l’application
CMD ["python", "app.py"]
