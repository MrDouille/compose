# 🌐 qBittorrent (via LinuxServer.io)

Ce dossier contient un fichier `docker-compose.yml` pour déployer **qBittorrent**, un client BitTorrent open source, via l’image maintenue par LinuxServer.io.

Il s’agit d’une interface légère et performante pour gérer vos téléchargements torrents avec Web UI intégrée.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Variables d’environnement

- `PUID=1000` : UID utilisateur local
- `PGID=1000` : GID groupe local
- `TZ=Etc/UTC` : Fuseau horaire
- `WEBUI_PORT=8080` : Port interne pour l’interface Web (WebUI)

### Volumes

- `/chemin/local/qbittorrent/config:/config` : Configuration et état du conteneur
- `/chemin/local/qbittorrent/downloads:/downloads` : Emplacement des fichiers téléchargés

### Ports exposés

- `8080:8080` → Interface Web
- `6881:6881/tcp` → Port BitTorrent TCP
- `6881:6881/udp` → Port BitTorrent UDP (DHT)

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

Le conteneur redémarrera automatiquement sauf en cas d’arrêt manuel.

---

## 📍 Accès

Une fois lancé, ouvrez votre navigateur à l’adresse suivante :

```
http://localhost:8080
```

> Identifiants par défaut (si non configurés) :  
> **Utilisateur :** admin  
> **Mot de passe :** adminadmin

---

## 📚 Références

- [Docker Hub - linuxserver/qbittorrent](https://hub.docker.com/r/linuxserver/qbittorrent)
- [Documentation qBittorrent](https://www.qbittorrent.org/)
