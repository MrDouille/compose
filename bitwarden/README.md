# 🔐 Vaultwarden (ex-Bitwarden_RS)

Ce dossier contient un `docker-compose.yml` pour déployer **Vaultwarden**, une alternative légère et compatible avec les clients Bitwarden officiels.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker compose up -d
```

---

## ⚙️ Configuration

### Ports exposés

- `8081:80` → Interface Web de Vaultwarden (personnalisé)

### Volumes

- `/path/to/bitwarden/data:/data` : Contient les données utilisateurs et la configuration

### Variables d’environnement

- `WEBSOCKET_ENABLED=true` : Active la synchronisation temps réel via WebSocket
- `SIGNUPS_ALLOWED=true` : Permet les inscriptions librement (recommandé à `false` en production)

---

## 🔁 Politique de redémarrage

```yaml
restart: always
```

---

## 📍 Accès

Une fois le conteneur lancé, accédez à votre coffre :

```
http://localhost:8081
```

Utilisez les clients Bitwarden officiels ou l’interface web.

---

## 📚 Références

- [Vaultwarden GitHub](https://github.com/dani-garcia/vaultwarden)
- [Vaultwarden Docker Hub](https://hub.docker.com/r/vaultwarden/server)
