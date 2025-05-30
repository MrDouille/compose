# 🥑 Apache Guacamole (Image oznu)

Ce dossier contient un fichier `docker-compose.yml` pour déployer **Apache Guacamole**, une passerelle d'accès distant sans client, accessible via un simple navigateur web.

L'image utilisée ici est un tout-en-un intégrant le serveur Guacamole, le client web, et le backend nécessaire.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Volumes

- `/chemin/local/guacamole:/config` : Contient les fichiers de configuration persistants

### Port exposé

- `8080:8080` → Interface Web Guacamole

---

## 🔁 Politique de redémarrage

> Ce `docker-compose.yml` n’inclut pas de directive `restart`, mais vous pouvez ajouter :

```yaml
restart: unless-stopped
```

---

## 📍 Accès

Une fois lancé, ouvrez votre navigateur à l’adresse :

```
http://localhost:8080
```

Identifiants par défaut :
- **Nom d’utilisateur :** guacadmin
- **Mot de passe :** guacadmin

Pensez à modifier ces identifiants après la première connexion.

---

## 📚 Références

- [Docker Hub - oznu/guacamole](https://hub.docker.com/r/oznu/guacamole)
- [Documentation Apache Guacamole](http://guacamole.apache.org/)
