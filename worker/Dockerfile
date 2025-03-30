# Étape 1 : Build avec le SDK .NET
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /app

# Copier les fichiers projet et restaurer les dépendances
COPY Worker.csproj ./
RUN dotnet restore

# Copier tous les fichiers et compiler l'application
COPY . ./
RUN dotnet publish -c Release -o /app/out

# Étape 2 : Exécution avec l'image runtime plus légère
FROM mcr.microsoft.com/dotnet/runtime:7.0
WORKDIR /app

# Copier les fichiers compilés
COPY --from=build /app/out ./

# Définir les variables d'environnement pour la connexion aux services externes
ENV REDIS_HOST=redis
ENV POSTGRES_HOST=postgres

# Exposer les ports (facultatif, car ce worker n'a pas de serveur HTTP)
# EXPOSE 80 

# Lancer l'application
CMD ["dotnet", "Worker.dll"]
