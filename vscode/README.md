# 🧑‍💻 Code Server (VS Code dans un navigateur)

Ce dossier contient un `docker-compose.yml` pour exécuter **code-server**, une version de Visual Studio Code accessible via navigateur, idéale pour travailler à distance ou dans des environnements isolés.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker compose up -d
```

---

## ⚙️ Configuration

### Ports exposés

- `8080:8080` → Interface web de VS Code

### Volumes

- `/path/to/code/data:/home/coder/project` : Répertoire de travail partagé avec le conteneur

### Variables d’environnement

- `PASSWORD` : Mot de passe requis pour se connecter à l’interface
- `TZ` : Fuseau horaire (ici configuré sur `Europe/Paris`)

---

## 🔁 Politique de redémarrage

> Ce fichier ne spécifie pas de stratégie `restart`. Tu peux ajouter :

```yaml
restart: unless-stopped
```

---

## 📍 Accès

Une fois le conteneur lancé, accède à ton IDE à l’adresse suivante :

```
http://localhost:8080
```

Connecte-toi avec le mot de passe défini dans la variable `PASSWORD`.

---

## 📚 Références

- [Docker Hub - codercom/code-server](https://hub.docker.com/r/codercom/code-server)
- [Documentation officielle](https://coder.com/docs/code-server/latest)
