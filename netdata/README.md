# 📊 Netdata

Ce dossier contient un `docker-compose.yml` pour déployer **Netdata**, une solution de monitoring en temps réel légère et puissante pour surveiller l’état de vos conteneurs et de votre système.

---

## 🚀 Lancer le conteneur

Installez [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/) si ce n’est pas déjà fait.

```bash
docker compose up -d
```

---

## ⚙️ Configuration

### Ports exposés

- `19999:19999` → Interface Web de Netdata

### Volumes montés

- `/path/to/netdata/config:/etc/netdata:ro` : Configuration en lecture seule
- `netdatalib:/var/lib/netdata` : Données d’historique
- `netdatacache:/var/cache/netdata` : Cache temporaire
- `/etc/passwd:/host/etc/passwd:ro`, `/etc/group:/host/etc/group:ro` : Utilisés pour identifier les utilisateurs
- `/proc:/host/proc:ro`, `/sys:/host/sys:ro` : Métriques système Linux
- `/etc/os-release:/host/etc/os-release:ro` : Informations sur la distribution hôte

### Sécurité

- `cap_add: SYS_PTRACE` : Permet le profiling des processus
- `security_opt: apparmor:unconfined` : Nécessaire pour certaines intégrations système

---

## 🔁 Politique de redémarrage

```yaml
restart: unless-stopped
```

---

## 📍 Accès

Accédez à l’interface Web de monitoring :

```
http://localhost:19999
```

---

## 📚 Références

- [Site officiel Netdata](https://www.netdata.cloud/)
- [Docker Hub - netdata/netdata](https://hub.docker.com/r/netdata/netdata)
