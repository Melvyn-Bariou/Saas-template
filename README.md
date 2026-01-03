# SaaS Template

Template SaaS fullstack avec :

- Backend : Spring Boot (Java 17)
- Frontend : Vue.js + Tailwind CSS + DaisyUI 4 et TypeScript
- Base de données : PostgreSQL
- Docker

## Structure du projet

```markdown
saas-template/
├── backend/ # Spring Boot
└── frontend/ # Vue.js + Tailwind + DaisyUI 4
```

## Prérequis

- Docker & Docker Compose installés
- Node.js et npm (pour le développement frontend)
- Java 17 (pour Maven si vous voulez compiler localement)

---

## Commandes Docker essentielles

```bash
# Arrêter tous les conteneurs et supprimer les orphelins
docker-compose down --remove-orphans
```

# Construire et lancer tous les services
docker-compose up --build
Accès aux services
Service	URL / Port
Frontend	http://localhost:3000
Backend	http://localhost:8080
PostgreSQL	localhost:5432

# Connexion à la base de données
Les paramètres par défaut du conteneur PostgreSQL (Docker Compose) :

DB : saasdb
User : saasuser
Password : saaspass
Port : 5432

Exemple avec psql :
```bash
psql -h localhost -U saasuser -d saasdb
Exemple avec un client GUI (DBeaver, TablePlus, pgAdmin) :
Host : localhost
```

Port : 5432
Database : saasdb
User : saasuser
Password : saaspass

Développement frontend
```bash
cd frontend
npm install
npm run dev
```

Accès : http://localhost:5173 (Vite dev server)

Développement backend
```bash
cd backend
./mvnw clean package
./mvnw spring-boot:run
```

Accès : http://localhost:8080

# Notes
Frontend et backend communiquent via API REST (à configurer dans Spring Boot + Vue.js)

Tailwind + DaisyUI sont déjà configurés

PostgreSQL est prêt à l’emploi via Docker, aucune installation locale nécessaire