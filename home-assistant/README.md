# 🏠 Home Assistant

Ce dossier contient un fichier `docker-compose.yml` pour déployer **Home Assistant**, une plateforme domotique open-source puissante permettant d’automatiser et de superviser votre maison connectée.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Volumes

- `/chemin/local/homeassistant:/config` : Contient toutes les données de configuration, automations, intégrations, etc.

### Variables d’environnement

- `TZ=Europe/Paris` : Fuseau horaire du conteneur (à adapter selon votre région)

### Ports exposés

- `8123:8123` → Interface web de Home Assistant

### Accès au matériel

- `privileged: true` : Nécessaire pour permettre l’accès à certains périphériques locaux (dongle Zigbee, clé USB, Bluetooth, etc.)

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

Le conteneur se relancera automatiquement sauf arrêt manuel.

---

## 📍 Accès

Une fois lancé, ouvrez votre navigateur à l’adresse suivante :

```
http://localhost:8123
```

---

## 📚 Références

- [Image officielle - ghcr.io/home-assistant/home-assistant](https://github.com/home-assistant/core)
- [Documentation Home Assistant](https://www.home-assistant.io/)
