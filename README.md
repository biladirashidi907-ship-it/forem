<div align="center">
  <br>
  <h1>ESTRA LINK 🌐</h1>
  <strong>Le réseau social éducatif qui connecte le savoir</strong>
</div>
<br>
<p align="center">
  <a href="https://github.com/estra-link/estra-link/actions/workflows/ci.yml">
    <img src="https://github.com/estra-link/estra-link/actions/workflows/ci.yml/badge.svg" alt="Build Status">
  </a>
  <a href="https://github.com/estra-link/estra-link/actions/workflows/cd.yml">
    <img src="https://github.com/estra-link/estra-link/actions/workflows/cd.yml/badge.svg" alt="Build Status">
  </a>
  <img src="https://img.shields.io/github/commit-activity/w/estra-link/estra-link" alt="GitHub commit activity">
  <a href="https://github.com/estra-link/estra-link/issues?q=is%3Aissue+is%3Aopen+label%3A%22ready+for+dev%22">
    <img src="https://img.shields.io/github/issues/estra-link/estra-link/ready%20for%20dev" alt="GitHub issues ready for dev">
  </a>
  <a href="https://gitpod.io/#https://github.com/estra-link/estra-link">
    <img src="https://img.shields.io/badge/setup-automated-blue?logo=gitpod" alt="GitPod badge">
  </a>
</p>

Bienvenue sur le code source d'**[ESTRA LINK](https://estra-link.com)**, la plateforme qui connecte étudiants, enseignants et passionnés de savoir. Nous sommes ravis de vous accueillir. Avec votre aide, nous pouvons construire un espace éducatif collaboratif, accessible et innovant pour toutes les communautés d'apprentissage.

## Qu'est-ce qu'ESTRA LINK ?

ESTRA LINK est une plateforme open source dédiée à l'éducation et au partage de connaissances. Elle permet de créer des communautés d'apprentissage où les membres peuvent échanger des ressources, participer à des discussions thématiques, suivre des parcours pédagogiques et construire leur profil académique. Notre mission est de démocratiser l'accès au savoir en connectant les apprenants du monde entier.

Nous croyons en une éducation inclusive et collaborative, où chaque voix compte et chaque connaissance mérite d'être partagée. ❤️

## Table des matières

- [Qu'est-ce qu'ESTRA LINK ?](#quest-ce-questra-link)
- [Table des matières](#table-des-matières)
- [Contribuer](#contribuer)
- [Pour commencer](#pour-commencer)
  - [Documentation d'installation](#documentation-dinstallation)
- [Documentation développeur](#documentation-développeur)
- [Déploiement avec Kamal](#déploiement-avec-kamal)
- [Signalement de vulnérabilités](#signalement-de-vulnérabilités)
- [Remerciements](#remerciements)
- [Licence](#licence)

## Contribuer

Nous acceptons les pull requests sur tous les tickets, quel que soit leur statut, dès lors qu'elles apportent une correction ou une amélioration. Bien que nous ne puissions garantir que chaque PR sera fusionnée, nous valorisons toutes les suggestions et contributions légitimes.

**Toutes les pull requests doivent inclure des tests appropriés.** Notre attention actuelle se porte principalement sur les tests de régression backend, tandis que les modifications frontend peuvent nécessiter une revue utilisateur plus approfondie.

Nous accueillons les pull requests assistées par IA, mais nous refuserons le "slop" — toutes les soumissions doivent maintenir des standards élevés de qualité de code et d'utilité concrète.

🤖 Les agents IA peuvent consulter `AGENTS.md` pour plus d'instructions. Pour les IDE et environnements spécifiques, ESTRA LINK synchronise également ces règles dans `.cursorrules`, `.windsurfrules` et `.github/copilot-instructions.md`.

Consultez également le [Guide de contribution à ESTRA LINK](https://docs.estra-link.com/contributing-guide) pour des directives plus détaillées.

## Pour commencer

Cette section fournit un guide de démarrage rapide. Si vous cherchez une installation plus complète (par exemple [pour macOS](https://docs.estra-link.com/getting-started/installation/mac)), référez-vous à notre [Documentation développeur](https://docs.estra-link.com/) complète.

Nous fonctionnons avec un backend [Rails](https://rubyonrails.org/) et une interface frontend moderne en [React](https://reactjs.org/).

**Prérequis important** : ESTRA LINK utilise des embeddings IA avancés pour la génération de flux personnalisés et les recommandations de contenu. Vous devez vous assurer que votre installation PostgreSQL dispose de l'extension `pgvector` (version 0.8.0 ou supérieure) pour supporter l'indexation HNSW. Cette extension de base de données est **obligatoire** pour exécuter les migrations et faire fonctionner l'application.

Pour installer `pgvector` :
- **macOS (Homebrew)** : `brew install pgvector`
- **Linux (Debian/Ubuntu)** : `sudo apt install postgresql-15-pgvector` (ajustez `15` selon votre version de PostgreSQL), ou compilez depuis les sources en suivant le [guide d'installation pgvector](https://github.com/pgvector/pgvector#installation).

La fourniture d'une clé API Gemini (`GEMINI_API_KEY`) pour générer les embeddings est entièrement optionnelle ; si elle est omise, l'application continuera à fonctionner normalement sans recommandations sémantiques.

Un aperçu plus complet de notre stack est disponible dans [notre documentation](https://docs.estra-link.com/technical-overview/stack).

Pour **lancer ESTRA LINK dans Gitpod**, rendez-vous sur [https://gitpod.io/#https://github.com/{votre_nom_utilisateur_github}/estra-link](https://gitpod.io/#https://github.com/{votre_nom_utilisateur_github}/estra-link).

Pour **lancer ESTRA LINK dans Ona** (anciennement Gitpod), le projet est entièrement configuré pour les environnements de développement Ona. Ouvrez simplement le projet dans Ona et l'environnement sera automatiquement configuré avec tous les services et dépendances nécessaires.

### Documentation d'installation

Consultez nos guides d'installation :

- [macOS, sans conteneurs](https://docs.estra-link.com/getting-started/installation/mac)
- [Linux, sans conteneurs](https://docs.estra-link.com/getting-started/installation/linux)

## Documentation développeur

[Consultez notre page de documentation dédiée pour plus de documentation technique](https://docs.estra-link.com). Veuillez noter que bien que la documentation soit un excellent point de départ, certaines parties peuvent être obsolètes au fil de l'évolution du projet.

## Déploiement avec Kamal (Beta)

ESTRA LINK est équipé de [Kamal 2](https://kamal-deploy.org/) pour vous permettre de déployer facilement l'application sur n'importe quel fournisseur cloud ou serveur bare metal.

Pour un guide complet, incluant les configurations des fournisseurs cloud (AWS, DigitalOcean, Hetzner, GCP), la gestion des secrets et les particularités de production spécifiques à ESTRA LINK, consultez le [Guide de déploiement Kamal](docs/kamal-deployment.md).

### Prérequis

Avant de déployer, assurez-vous d'avoir :
1. Un accès SSH à votre/vos serveur(s) cible(s).
2. Docker installé sur votre machine locale et le(s) serveur(s) cible(s).
3. Un compte de registre de conteneurs Docker (ex : GitHub Container Registry, Docker Hub).

### Configuration

1. **Configuration de déploiement** : Ouvrez [config/deploy.yml](config/deploy.yml) et mettez à jour :
   - Votre nom d'utilisateur et identifiants de registre.
   - Votre nom de domaine dans la section `proxy`.
2. **Configuration de l'environnement et des secrets** : Définissez les variables d'environnement suivantes sur votre machine locale :
   - `KAMAL_WEB_IP` / `KAMAL_JOB_IP` / `KAMAL_DB_IP` / `KAMAL_REDIS_IP` : Les adresses IP de vos serveurs (par défaut `192.168.0.1`).
   - `KAMAL_REGISTRY_PASSWORD` : Token d'accès pour votre registre de conteneurs Docker.
   - `RAILS_MASTER_KEY` : Votre clé maître Rails.
   - `DATABASE_URL` : Chaîne de connexion pour PostgreSQL. Ceci est toujours requis. Si vous utilisez l'accessoire Kamal postgres, définissez-le sur le hostname de l'accessoire (ex : `postgresql://postgres:password@estra-link-postgres:5432/estra_link_production`).
   - `POSTGRES_PASSWORD` : Mot de passe root pour l'accessoire PostgreSQL (si vous l'utilisez).

### Déploiement de l'application

Exécutez les commandes suivantes pour configurer et déployer l'application :

```bash
# 1. Vérifier que votre configuration est valide
bundle exec kamal config

# 2. Démarrer les accessoires, construire & pousser l'image docker, et déployer l'application
bundle exec kamal setup

# 3. Déploiements suivants (mises à jour progressives)
bundle exec kamal deploy