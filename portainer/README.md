# 🧭 Portainer CE

Ce dossier contient un fichier `docker-compose.yml` permettant de déployer **Portainer Community Edition**, une interface web légère pour gérer vos environnements Docker.

Portainer simplifie l'administration de vos conteneurs, volumes, réseaux et images via une interface graphique intuitive.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Volumes

- `/var/run/docker.sock:/var/run/docker.sock` : Permet à Portainer de communiquer avec le daemon Docker
- `/chemin/local/portainer/data:/data` : Stocke les données de Portainer de manière persistante

### Port exposé

- `9000:9000` → Interface web de Portainer

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

Le conteneur redémarrera automatiquement sauf en cas d’arrêt manuel.

---

## 📍 Accès

Une fois le conteneur lancé, ouvrez votre navigateur à l’adresse suivante :

```
http://localhost:9000
```

Lors du premier accès, vous serez invité à créer un utilisateur administrateur.

---

## 📚 Références

- [Page Docker Hub - portainer/portainer-ce](https://hub.docker.com/r/portainer/portainer-ce)
- [Documentation officielle Portainer](https://docs.portainer.io/)
