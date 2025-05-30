# 🌩️ Cloudflare Tunnel (cloudflared)

Ce dossier contient un fichier `docker-compose.yml` pour déployer un tunnel sécurisé avec **Cloudflare Tunnel** (via l'outil `cloudflared`), permettant d'exposer des services locaux à Internet sans ouvrir de port sur votre routeur.

---

## 🚀 Lancer le conteneur

Avant de lancer le tunnel, assurez-vous d’avoir obtenu un **jeton d’accès** auprès de Cloudflare.  
[Documentation officielle : créer un tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/)

Ajoutez ensuite le jeton dans le `docker-compose.yml` ou utilisez une variable d’environnement.

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Commande

```yaml
command: >
  tunnel --no-autoupdate run --token VOTRE_TOKEN_ICI
```

> **Remarque :** Il est recommandé de ne pas stocker le jeton en clair. Préférez une variable d’environnement ou un fichier `.env`.

### Image

- `cloudflare/cloudflared:latest` : Image officielle `cloudflared`

---

## 🔁 Politique de redémarrage

```yaml
restart: always
```

Le conteneur redémarrera automatiquement en cas d’erreur ou après un redémarrage de l’hôte.

---

## 📚 Références

- [Docker Hub - cloudflare/cloudflared](https://hub.docker.com/r/cloudflare/cloudflared)
- [Documentation Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/)
