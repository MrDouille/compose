
# qBittorrent

Ce dossier contient la stack Docker Compose pour **qBittorrent**, un client BitTorrent avec interface Web.

## Configuration

Les paramètres importants sont définis dans le fichier `.env` à la racine de ce dossier.

## Variables d'environnement

| Variable    | Description                             | Exemple       |
|-------------|---------------------------------------|---------------|
| PUID        | UID utilisateur pour les permissions  | 1000          |
| PGID        | GID groupe pour les permissions       | 1000          |
| TZ          | Fuseau horaire                       | Europe/Paris  |
| WEBUI_PORT  | Port pour l'interface Web (optionnel) | 8080          |

## Lancement

Pour démarrer le conteneur :

```bash
docker-compose up -d
```

Pour arrêter le conteneur :

```bash
docker-compose down
```
