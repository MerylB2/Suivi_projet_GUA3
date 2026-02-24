# RESUME — TaskFlow
**Leslie & Sandra | Licence Pro Full Stack | 2025–2026**

---

## Le Projet

TaskFlow est une application web de gestion de tâches permettant à un utilisateur d'organiser et de suivre ses activités quotidiennes. L'utilisateur peut créer un compte, se connecter, créer, modifier, filtrer, rechercher et supprimer des tâches, avec gestion des priorités, des statuts et des notifications.

**Stack retenue (fusion des deux propositions) :**

| Couche | Technologie |
|--------|-------------|
| Frontend | React.js |
| Backend | Node.js / Django |
| Base de données | PostgreSQL |
| Communication | API REST |
| Authentification | JWT |
| Versioning | Git |

---

## Analyse des Deux Propositions

### Ce que Leslie a bien fait
La proposition de Leslie est la plus complète et la mieux structurée des deux. Elle couvre tous les éléments attendus pour un Mini-Projet 1 : introduction, objectifs, besoins fonctionnels et non-fonctionnels, contraintes techniques, architecture, modélisation des données, endpoints API, flux de données, structure de projet et conclusion. Le schéma logique et le flux de données sont clairs et corrects. La séparation des responsabilités par couche est bien articulée et directement alignée sur le Chapitre 1 du cours.

### Ce que Sandra a bien fait
Sandra a identifié des fonctionnalités importantes que Leslie n'a pas incluses : l'authentification (création de compte, connexion, déconnexion sécurisée), le filtrage par statut, la recherche par mot-clé, et la gestion des notifications et rappels. Ces ajouts enrichissent le périmètre fonctionnel du projet. Son diagramme architectural décrit bien les sous-composants de chaque couche (middleware, repositories, gestion de l'état global).

### Ce qui manque dans les deux propositions

**Chez Leslie :**
- Pas d'authentification — c'est un oubli majeur pour une application avec des données utilisateur
- Le champ `created_ad` dans la table tasks est une faute de frappe (`created_at`)
- La base de données hésite entre MySQL et PostgreSQL — il faut trancher
- La conclusion est trop courte et générique
- Le fichier est un notebook Jupyter (.ipynb) — un document de conception devrait être un fichier Markdown ou PDF

**Chez Sandra :**
- Pas de modélisation des données (table, champs, types) — section manquante
- Pas d'endpoints API définis — section vide
- Pas de structure de projet — section vide
- Pas de flux de données
- La stack mentionne Flask-Login comme outil d'authentification dans un projet Django — c'est incohérent, Flask et Django sont deux frameworks distincts
- Le fichier est un notebook Jupyter avec le code dans une cellule `code` au lieu d'une cellule `markdown` — erreur de format
- Le niveau de détail est insuffisant pour un document de conception

---

## Problèmes Identifiés — Communs aux Deux

**Choix de stack non unifié.**
Leslie propose Node.js, Sandra propose Django. Puisque vous travaillez désormais ensemble sur un seul projet, il faut choisir un seul back-end. Ma recommandation : Node.js/Express, qui est aligné sur le Chapitre 3 du cours. Si vous souhaitez Django pour une raison précise, argumentez ce choix dans votre document.

**Pas de répartition des rôles.**
Aucune des deux propositions ne mentionne qui fait quoi. C'est à définir immédiatement.

**Le nom "Todo-list" (Sandra) est trop générique.**
"TaskFlow" (issu de la structure de Leslie) est plus porteur. Je recommande de conserver TaskFlow comme nom officiel du projet.

**Aucune des deux ne mentionne la validation côté serveur comme obligatoire.**
La validation côté client existe chez Leslie, mais la validation côté serveur (qui est non négociable selon le Chapitre 3) n'est pas explicitement définie dans les endpoints.

---

## Proposition de Répartition des Rôles

**Leslie — Architecture + Documentation + Frontend**
Sa proposition montre une maîtrise plus claire de la structure globale et de la séparation des couches. Elle prend en charge les composants React, les pages, les services (appels API), et la documentation technique.

**Sandra — Backend + Base de données + Authentification**
Elle a identifié les besoins d'authentification que Leslie a omis. Elle prend en charge Node.js/Express, les controllers, les routes, les modèles, la base de données PostgreSQL, et le système de connexion/déconnexion JWT.

---

## Fonctionnalités Retenues pour le MVP (Fusion des Deux)

**Authentification (apport de Sandra)**
- Création de compte
- Connexion / déconnexion sécurisée
- Protection des routes (accès uniquement aux tâches de l'utilisateur connecté)

**Gestion des tâches (apport des deux)**
- Créer une tâche avec titre, description, priorité, date de création automatique
- Modifier une tâche (titre, description, priorité, statut)
- Supprimer une tâche avec confirmation
- Afficher la liste complète des tâches
- Consulter le détail d'une tâche
- Filtrer par statut (apport de Sandra)
- Rechercher par mot-clé (apport de Sandra)

**Fonctionnalités post-MVP (trop complexes pour le premier sprint)**
- Notifications et rappels (apport de Sandra) — à prévoir en phase 2

---

## Modélisation des Données Consolidée

**Table : users**

| Champ | Type | Description |
|-------|------|-------------|
| id | INT | Identifiant unique |
| email | VARCHAR | Email unique |
| password_hash | VARCHAR | Mot de passe haché |
| created_at | DATE | Date de création |

**Table : tasks**

| Champ | Type | Description |
|-------|------|-------------|
| id | INT | Identifiant unique |
| user_id | INT (FK) | Référence à l'utilisateur |
| title | VARCHAR | Titre de la tâche |
| description | TEXT | Description |
| priority | ENUM | low / medium / high |
| status | BOOLEAN | Terminé ou non |
| created_at | DATE | Date de création automatique |

---

## Endpoints API Consolidés

| CRUD | Méthode | URL | Action |
|------|---------|-----|--------|
| - | POST | /auth/register | Créer un compte |
| - | POST | /auth/login | Se connecter |
| - | POST | /auth/logout | Se déconnecter |
| Create | POST | /tasks | Créer une tâche |
| Read | GET | /tasks | Lire toutes les tâches |
| Read | GET | /tasks/:id | Lire une tâche |
| Read | GET | /tasks?status= | Filtrer par statut |
| Read | GET | /tasks?search= | Rechercher par mot-clé |
| Update | PUT | /tasks/:id | Modifier une tâche |
| Delete | DELETE | /tasks/:id | Supprimer une tâche |

---

## Structure du Projet Consolidée

```
├── README.md
├── taskflow/
│   ├── backend/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   └── routes/
│   └── frontend/
│       └── src/
│           ├── components/
│           ├── pages/
│           └── services/
```

---

## Liaison avec les Chapitres du Cours

**Chapitre 1 — Architecture Full Stack**
Les deux propositions appliquent correctement la séparation en 3 couches. Leslie l'a particulièrement bien détaillée avec les responsabilités par couche. Cette séparation doit être maintenue et renforcée dans le projet fusionné.

**Chapitre 2 — Front-end Avancé**
Les composants React identifiés dans la structure correspondent aux attentes du Mini-Projet 2 : TaskForm (création/modification), TaskCard (affichage d'une tâche), TaskList (liste avec filtres). Sandra a ajouté les pages login et dashboard qui enrichissent l'architecture frontend.

**Chapitre 3 — Back-end Avancé**
L'authentification identifiée par Sandra et les controllers/routes de Leslie couvrent les fondamentaux du Chapitre 3 : logique métier, validation serveur, JWT, gestion des erreurs. Il manque encore la validation explicite côté serveur sur chaque endpoint — à ajouter dans le document de conception final.