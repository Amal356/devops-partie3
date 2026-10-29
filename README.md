# DevOps & Cloud – Partie 3 : Conteneurs et API

**Étudiante :** Amal Jemli – Master DevOps et Cloud Computing (2026/2027)
**Énoncés :** [Partie 3 – TP7 et TP8](https://docs.teknolabs.net/courses/devops-cloud/partie-3-conteneurs-api/)

| TP  | Sujet | Outils | Dossier |
|-----|-------|--------|---------|
| TP7 | Images Docker petites et sûres, pile Compose, multi-architecture | Docker 29.8, Compose v5.6, Buildx v0.37, Trivy, PostgreSQL 17, Adminer, Nginx | [tp7-docker-compose](tp7-docker-compose) |
| TP8 | API Express sécurisée et testée | Express, Zod, Helmet, express-rate-limit, Vitest, Supertest | [tp8-api-express-tests](tp8-api-express-tests) |

Chaque dossier contient son README (étapes, explications, réponses aux questions), le code et un dossier `captures/`.

## Environnement

VM VirtualBox `ubuntu-server-26` (Ubuntu Server 26.04.1 LTS, 4 Go RAM, 2 vCPU, disque 50 Go), réseau host-only `192.168.56.40`.

## Sécurité

- Aucun secret dans le dépôt : `.env` est exclu par le `.gitignore`, seul `.env.example` est versionné.
- Image publiée sur Docker Hub : `amal878/visits-app:1.0.0` (amd64 + arm64) ; identifiant supprimé avec `docker logout`.
