
# Plex Media Server

Ce dossier contient la stack Docker Compose pour **Plex Media Server**, un serveur de streaming média personnel.

## Configuration

Les paramètres importants sont définis dans le fichier `.env` à la racine de ce dossier.

## Variables d'environnement

| Variable    | Description                                        | Exemple       |
|-------------|--------------------------------------------------|---------------|
| PUID        | UID utilisateur pour les permissions             | 1000          |
| PGID        | GID groupe pour les permissions                   | 1000          |
| TZ          | Fuseau horaire                                   | Europe/Paris  |
| PLEX_CLAIM  | Token de réclamation Plex (optionnel)             | (vide par défaut) |

## Lancement

Pour démarrer le conteneur :

```bash
docker-compose up -d
```

Pour arrêter le conteneur :

```bash
docker-compose down
```
