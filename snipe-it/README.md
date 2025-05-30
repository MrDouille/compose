# 🧾 Snipe-IT + MySQL

Ce dossier contient un `docker-compose.yml` permettant de déployer **Snipe-IT**, une application de gestion de parc informatique (ITAM), avec une base de données **MySQL**.

---

## 🚀 Lancer la stack

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker compose up -d
```

---

## ⚙️ Configuration

### Services

- **snipe-mysql** : Serveur MySQL pour stocker les données
- **snipe-it** : Application web Snipe-IT (basée sur Laravel)

### Ports exposés

- `9300:3306` → Port MySQL (accès local ou depuis d'autres conteneurs si nécessaire)
- `9090:80` → Interface Web de Snipe-IT

### Variables importantes

#### MySQL

- `MYSQL_ROOT_PASSWORD` : mot de passe root (non utilisé directement par Snipe-IT)
- `MYSQL_DATABASE`, `MYSQL_USER`, `MYSQL_PASSWORD` : informations d'accès pour Snipe-IT

#### Snipe-IT

- `APP_ENV`, `APP_DEBUG` : environnement de production recommandé
- `APP_KEY` : clé Laravel (générée via `php artisan key:generate`)
- `APP_URL` : URL publique d'accès à l'application
- `DB_HOST`, `DB_PORT`, `DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD` : connexion à la base
- `TIMEZONE` : fuseau horaire (ex. `Europe/Paris`)

---

## 🗃️ Volumes

- `/path/to/mysql/data:/var/lib/mysql` : Données persistantes de la base MySQL
- `/path/to/snipeit/data:/var/lib/snipeit` : Fichiers Snipe-IT (logs, fichiers uploadés, etc.)

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

---

## 📍 Accès

Une fois lancé, accédez à l'interface web :

```
http://localhost:9090
```

Suivez l’assistant d’installation pour terminer la configuration de Snipe-IT.

---

## 📚 Références

- [Snipe-IT documentation](https://snipeitapp.com/docs)
- [Docker Hub - snipe/snipe-it](https://hub.docker.com/r/snipe/snipe-it)
