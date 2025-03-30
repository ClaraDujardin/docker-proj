# 1. Utiliser une image Node.js
FROM node:18

# 2. Définir le répertoire de travail
WORKDIR /app

# 3. Copier les fichiers nécessaires
COPY package.json package-lock.json server.js /app/
COPY views /app/views

# 4. Installer les dépendances
RUN npm install

# 5. Exposer le port utilisé par Express
EXPOSE 8888

# 6. Lancer l’application
CMD ["node", "server.js"]
