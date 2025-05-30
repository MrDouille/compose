# 🧿 Pi-hole

Ce dossier contient un fichier `docker-compose.yml` pour déployer **Pi-hole**, un serveur DNS qui bloque la publicité et les trackers au niveau réseau.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker compose up -d
```

---

## ⚙️ Configuration

### Ports exposés

- `53` (TCP/UDP) : Port DNS (obligatoire pour le fonctionnement)
- `67` (UDP) : Port DHCP (optionnel, uniquement si vous activez le serveur DHCP)
- `8080:80` : Interface Web HTTP
- `8443:443` : Interface Web HTTPS

> Les ports HTTP/HTTPS sont personnalisables dans le fichier compose.

### Volumes

- `/path/to/pihole/config:/etc/pihole/` : Contient la configuration principale de Pi-hole
- `/path/to/dnsmasq/config:/etc/dnsmasq.d/` : Fichiers de configuration DNSMasq

### Autres options

- `cap_add: NET_ADMIN` : Requis si DHCP est utilisé
- `TZ` : Fuseau horaire (ex. `Europe/Paris`)

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

---

## 📍 Accès

Une fois lancé, ouvrez votre navigateur à l’adresse suivante :

```
http://localhost:8080
```

(ou remplacez `localhost` par l’IP de votre machine Docker)

---

## 📚 Références

- [Documentation Pi-hole](https://docs.pi-hole.net/)
- [Pi-hole Docker GitHub](https://github.com/pi-hole/docker-pi-hole)
