# 🛡️ AdGuard Home

Ce dossier contient un fichier `docker-compose.yml` pour déployer **AdGuard Home**, un serveur DNS personnalisé permettant de bloquer la publicité, les traqueurs et bien plus, au niveau réseau.

---

## 🚀 Lancer le conteneur

Assurez-vous d’avoir installé [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/).

```bash
docker-compose up -d
```

---

## ⚙️ Configuration

### Ports exposés

- `53:53/tcp` et `53:53/udp` → Requêtes DNS classiques
- `853:853/tcp` → DNS-over-TLS
- `9002:80/tcp` → Interface Web HTTP (personnalisée)
- `9003:443/tcp` → Interface Web HTTPS
- `9004:3000/tcp` → Port d’administration (local/web)
- *(optionnels)* `67/udp`, `68/tcp`, `68/udp` pour le mode DHCP

### Volumes

- `/chemin/local/adguard/conf:/opt/adguardhome/conf` : Configuration persistante
- `/chemin/local/adguard/data:/opt/adguardhome/work` : Données d’activité (logs, états)
- `/chemin/local/adguard/certs:/opt/adguardhome/certs` : Certificats TLS/SSL (configurables via l’interface)

### Labels

- `com.centurylinklabs.watchtower.enable=true` : Permet la mise à jour automatique avec [Watchtower](https://containrrr.dev/watchtower/)

---

## 🔁 Politique de redémarrage

```yaml
restart: always
```

Le conteneur sera automatiquement relancé en cas de crash ou après redémarrage de la machine.

---

## 📍 Accès

- Interface web (HTTP) : `http://localhost:9002`
- Interface sécurisée (HTTPS) : `https://localhost:9003`
- Administration (API/console) : `http://localhost:9004`

---

## 📚 Références

- [Docker Hub - adguard/adguardhome](https://hub.docker.com/r/adguard/adguardhome)
- [Documentation AdGuard Home](https://github.com/AdguardTeam/AdGuardHome)
