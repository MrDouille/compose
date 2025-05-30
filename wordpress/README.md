# 📝 WordPress + MySQL

Ce dossier contient un `docker-compose.yml` prêt à l’emploi pour déployer **WordPress** avec une base de données **MySQL**, le tout en conteneur Docker.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker compose up -d
```

---

## ⚙️ Configuration

### Services

- **WordPress** : CMS accessible via un navigateur web
- **MySQL** : Base de données persistante pour stocker les articles, comptes, etc.

### Ports exposés

- `8080:80` → Interface Web WordPress (personnalisé pour éviter les conflits)

### Variables d’environnement (WordPress)

- `WORDPRESS_DB_HOST` : nom du service MySQL (`db`)
- `WORDPRESS_DB_USER` : identifiant de la base
- `WORDPRESS_DB_PASSWORD` : mot de passe associé
- `WORDPRESS_DB_NAME` : nom de la base de données

### Variables d’environnement (MySQL)

- `MYSQL_DATABASE` : nom de la base créée automatiquement
- `MYSQL_USER` : utilisateur
- `MYSQL_PASSWORD` : mot de passe utilisateur
- `MYSQL_RANDOM_ROOT_PASSWORD` : empêche l'accès root (mot de passe aléatoire)

### Volumes

- `wordpress_data:/var/www/html` : Stockage persistant des fichiers WordPress
- `db_data:/var/lib/mysql` : Données persistantes de MySQL

---

## 🔁 Politique de redémarrage

```yaml
restart: always
```

Les deux conteneurs redémarrent automatiquement si le système est relancé ou en cas de plantage.

---

## 📍 Accès

Une fois lancé, accédez à WordPress via :

```
http://localhost:8080
```

Suivez l’assistant de configuration pour finaliser l’installation.

---

## 📚 Références

- [Image WordPress sur Docker Hub](https://hub.docker.com/_/wordpress)
- [Image MySQL sur Docker Hub](https://hub.docker.com/_/mysql)
- [Documentation WordPress](https://wordpress.org/support/)
