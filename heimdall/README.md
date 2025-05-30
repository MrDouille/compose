# 🛡️ Heimdall

Ce dossier contient un fichier `docker-compose.yml` permettant de déployer rapidement **Heimdall**, une page d’accueil de serveur personnalisable et légère.

Heimdall permet de centraliser et de présenter de manière visuelle vos applications web et services auto-hébergés.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Variables d’environnement

- `PUID=1000` : UID de l'utilisateur local (utilisé pour les permissions des fichiers)
- `PGID=1000` : GID du groupe local
- `TZ=Etc/UTC` : Fuseau horaire (à adapter selon votre zone)

### Volumes

- `/chemin/local/heimdall/config:/config` : Stocke la configuration de Heimdall de manière persistante

### Ports exposés

- `10014:80` → Interface web (HTTP)
- `9443:443` → Interface sécurisée (HTTPS)

Modifiez les ports à gauche si nécessaire pour éviter des conflits avec d’autres services sur votre machine.

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

Le conteneur redémarrera automatiquement sauf en cas d’arrêt manuel.

---

## 📍 Accès

Une fois démarré, ouvrez votre navigateur à l’adresse :

```
http://localhost:10014
```

Ou en HTTPS :

```
https://localhost:9443
```

---

## 📚 Références

- [Page Docker Hub de Heimdall (LinuxServer.io)](https://hub.docker.com/r/linuxserver/heimdall)
- [Documentation officielle Heimdall](https://heimdall.site)
