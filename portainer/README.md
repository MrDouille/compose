
# Portainer CE

Ce dossier contient la stack Docker Compose pour **Portainer Community Edition**, un outil de gestion Docker via une interface Web.

## Configuration

Les paramètres importants sont définis dans le fichier `.env` à la racine de ce dossier.

## Variables d'environnement

| Variable    | Description                       | Exemple       |
|-------------|---------------------------------|---------------|
| PUID        | UID utilisateur (facultatif)     | 1000          |
| PGID        | GID groupe (facultatif)          | 1000          |
| TZ          | Fuseau horaire (facultatif)     | Europe/Paris  |

## Lancement

Pour démarrer le conteneur :

```bash
docker-compose up -d
```

Pour arrêter le conteneur :

```bash
docker-compose down
```
