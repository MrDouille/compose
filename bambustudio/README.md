# 🧵 Bambu Studio (via LinuxServer.io)

Ce dossier contient un fichier `docker-compose.yml` pour déployer **Bambu Studio**, l’interface de gestion et de préparation d’impression 3D pour les imprimantes Bambu Lab, packagée par LinuxServer.io.

Cette version s'exécute dans un conteneur accessible via une interface web.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Variables d’environnement

- `PUID=1000` : UID de l'utilisateur (adapter selon votre système)
- `PGID=1000` : GID du groupe (adapter selon votre système)
- `TZ=Etc/UTC` : Fuseau horaire
- `DARK_MODE=true` : Active le thème sombre (optionnel)

### Volumes

- `/chemin/local/bambu/config:/config` : Stocke les préférences et profils utilisateurs

### Ports exposés

- `8383:3000` → Interface principale Web de Bambu Studio
- `8484:3001` → Port secondaire (WebSocket/API locale selon la version)

### Sécurité

- `security_opt: seccomp:unconfined` : Option utile si certaines fonctions graphiques posent problème (à utiliser avec précaution)

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

Le conteneur redémarre automatiquement sauf arrêt manuel.

---

## 📍 Accès

Ouvrez votre navigateur à l’adresse suivante :

```
http://localhost:8383
```

---

## 📚 Références

- [Docker Hub - linuxserver/bambustudio](https://hub.docker.com/r/linuxserver/bambustudio)
- [Site officiel Bambu Lab](https://bambulab.com/)
