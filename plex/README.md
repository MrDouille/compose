# 🎬 Plex Media Server

Ce dossier contient un fichier `docker-compose.yml` permettant de déployer **Plex Media Server**, une plateforme de gestion et de streaming multimédia personnel.

Plex vous permet de centraliser vos films, séries et médias personnels et d’y accéder depuis n’importe quel appareil.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Variables d’environnement

- `PLEX_CLAIM=` : (optionnel) Token pour lier votre serveur à un compte Plex ([générer ici](https://www.plex.tv/claim))
- `TZ=Etc/UTC` : Fuseau horaire (à adapter)
- `PLEX_UID=1000` : UID de l'utilisateur local
- `PLEX_GID=1000` : GID du groupe local

### Volumes

- `/chemin/local/plex/config:/config` : Configuration persistante de Plex
- `/chemin/local/plex/tvshows:/data/tvshows` : Dossier des séries TV
- `/chemin/local/plex/movies:/data/movies` : Dossier des films

### Ports exposés

- `32400:32400` → Interface web et API principale
- `3005`, `8324`, `32469` → Services supplémentaires (DLNA, remote, etc.)

Adaptez les chemins locaux et les ports si nécessaire selon votre système.

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

Le conteneur redémarrera automatiquement sauf en cas d’arrêt manuel.

---

## 📍 Accès

Une fois démarré, ouvrez votre navigateur à l’adresse suivante :

```
http://localhost:32400/web
```

---

## 📚 Références

- [Docker Hub - plexinc/pms-docker](https://hub.docker.com/r/plexinc/pms-docker)
- [Documentation officielle Plex](https://support.plex.tv/)
