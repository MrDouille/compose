# 📦 Docker Compose Library

Bienvenue sur mon dépôt **`compose`** !
Ce dépôt regroupe une collection de stacks Docker Compose prêtes à l'emploi, pour déployer facilement divers services (auto-hébergement, dev, outils réseau, etc.).

Chaque service est isolé dans son propre dossier, avec ses fichiers nécessaires (`docker-compose.yml`, `.env`, etc.), pour une utilisation simple et modulaire.

---

## 📁 Structure du dépôt

📘 Chaque application contient désormais un fichier `README.md` dédié dans son dossier. Il explique comment déployer et configurer le service associé.

```bash
compose/
├── nginx/
│   ├── docker-compose.yml
│   └── .env
├── portainer/
│   └── docker-compose.yml
├── jellyfin/
│   ├── docker-compose.yml
│   └── .env
└── README.md
```

> 📂 Chaque dossier = un service autonome
> 📄 Le fichier `docker-compose.yml` est la base de chaque stack
> 🛠️ Un fichier `.env` est fourni lorsque nécessaire

---

## 🚀 Utilisation

1. Installe [Docker](https://docs.docker.com/get-docker/) et [Docker Compose](https://docs.docker.com/compose/install/)
2. Clone ce dépôt :
   ```bash
   git clone https://github.com/MrDouille/compose.git
   cd compose/nom_du_service
   ```
3. Adapte les variables dans `.env` si présent
4. Lance le service :
   ```bash
   docker compose up -d
   ```

---

## ⚙️ Prérequis

- Docker 🐳 (version récente)
- Docker Compose v2 recommandé (`docker compose` et non `docker-compose`)
- Connaissances de base en réseau / volumes / variables d’environnement

---

## ✅ Bonnes pratiques

- Les ports, volumes et chemins peuvent être modifiés à ta convenance
- Ne pas exposer inutilement les services en public (sécurité ! 🔒)
- Vérifie que les variables `.env` sont adaptées à ton environnement
- Tu peux forker ce repo et y ajouter tes propres stacks

---

## 🙌 Contribuer

Tu veux proposer une amélioration ou partager un service ?
Les contributions sont les bienvenues via **pull request** ou **issues** !

---

## 📄 Licence

Ce dépôt est sous licence [MIT](LICENSE).
Utilisation libre, mais merci de ne pas inclure d'informations sensibles dans les fichiers de configuration partagés publiquement.

---

> ✉️ Pour toute question ou suggestion, tu peux ouvrir une issue ici sur GitHub.1~# 📦 Docker Compose Library

Bienvenue sur mon dépôt **`compose`** !
Ce dépôt regroupe une collection de stacks Docker Compose prêtes à l'emploi, pour déployer facilement divers services (auto-hébergement, dev, outils réseau, etc.).

Chaque service est isolé dans son propre dossier, avec ses fichiers nécessaires (`docker-compose.yml`, `.env`, etc.), pour une utilisation simple et modulaire.

---

## 📁 Structure du dépôt

📘 Chaque application contient désormais un fichier `README.md` dédié dans son dossier. Il explique comment déployer et configurer le service associé.

```bash
compose/
├── nginx/
│   ├── docker-compose.yml
│   └── .env
├── portainer/
│   └── docker-compose.yml
├── jellyfin/
│   ├── docker-compose.yml
│   └── .env
└── README.md
```

> 📂 Chaque dossier = un service autonome
> 📄 Le fichier `docker-compose.yml` est la base de chaque stack
> 🛠️ Un fichier `.env` est fourni lorsque nécessaire

---

## 🚀 Utilisation

1. Installe [Docker](https://docs.docker.com/get-docker/) et [Docker Compose](https://docs.docker.com/compose/install/)
2. Clone ce dépôt :
   ```bash
   git clone https://github.com/MrDouille/compose.git
   cd compose/nom_du_service
   ```
3. Adapte les variables dans `.env` si présent
4. Lance le service :
   ```bash
   docker compose up -d
   ```

---

## ⚙️ Prérequis

- Docker 🐳 (version récente)
- Docker Compose v2 recommandé (`docker compose` et non `docker-compose`)
- Connaissances de base en réseau / volumes / variables d’environnement

---

## ✅ Bonnes pratiques

- Les ports, volumes et chemins peuvent être modifiés à ta convenance
- Ne pas exposer inutilement les services en public (sécurité ! 🔒)
- Vérifie que les variables `.env` sont adaptées à ton environnement
- Tu peux forker ce repo et y ajouter tes propres stacks

---

## 🙌 Contribuer

Tu veux proposer une amélioration ou partager un service ?
Les contributions sont les bienvenues via **pull request** ou **issues** !

---

## 📄 Licence

Ce dépôt est sous licence [MIT](LICENSE).
Utilisation libre, mais merci de ne pas inclure d'informations sensibles dans les fichiers de configuration partagés publiquement.

---

> ✉️ Pour toute question ou suggestion, tu peux ouvrir une issue ici sur GitHub.
