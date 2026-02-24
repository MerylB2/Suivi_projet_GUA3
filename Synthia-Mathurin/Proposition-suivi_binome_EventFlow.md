

---

# Suivi de projet — EventFlow (binôme)
**Destinataires : Synthia Donfack & Mathurin**
**Cours : Bachelor CDA — Promotion 2025–2026**

---

Ce document est une directive de suivi. Il précise la répartition des responsabilités, le calendrier attendu, les livrables prioritaires et les simplifications acceptées pour produire un MVP démontrable devant le jury.

## Répartition des rôles (attendue)

- **Synthia — Back‑end, orchestration et modules ML (lead technique back)**
	- Responsabilités : architecture Django, base de données, API REST, traitement asynchrone (Celery), intégration des modules ML requis pour le MVP.
- **Mathurin — Front‑end, intégration et expérience utilisateur (lead front)**
	- Responsabilités : projet React Native/Expo, composants UI, routing, intégration des appels API, rendu des mini‑sites à partir du JSON produit côté back.

Les deux doivent collaborer étroitement sur : définition des contrats d'API, scénarios de tests d'intégration, déploiement et préparation de la démonstration.

## Plan de travail et jalons

Les phases ci‑dessous sont datées à titre indicatif. Respectez les livrables indiqués à la fin de chaque phase.

### Phase 1 — Fondations (Semaines 1–2)

- Back‑end (Synthia) : initialisation Django + PostgreSQL, définition des modèles (User, Event, Invitation), implémentation des endpoints d'authentification (register, login, refresh), préparation de l'environnement Celery.
- Front‑end (Mathurin) : initialisation React Native + Expo, structure de navigation, composants de base et écrans d'authentification.

Livrable de la phase : authentification end‑to‑end (front connecté au back) et dépôt initial partagé.

### Phase 2 — Création d'événement & génération de templates (Semaines 3–6)

- Back‑end (Synthia) : endpoints CRUD événements, intégration du service de génération de templates (API Claude ou équivalent), gestion de l'upload et du traitement asynchrone des images, support des sous‑domaines dynamiques (simulation acceptable pour la démo).
- Front‑end (Mathurin) : assistant de création (flow en 6 étapes), sélection/aperçu de templates, moteur de rendu des mini‑sites depuis le JSON, écran de publication.

Livrable de la phase : création complète d'un événement abouti et publication du mini‑site.

### Phase 3 — Invitations et participation (Semaines 7–9)

- Back‑end (Synthia) : génération de liens d'invitation sécurisés, envoi de SMS via Twilio (ou simulation), WebSocket pour mise à jour temps réel, gestion RSVP et questionnaires.
- Front‑end (Mathurin) : interface invité (RSVP), tableau de bord organisateur temps réel, notifications in‑app.

Livrable de la phase : parcours invité complet (réception du lien, réponse, visibilité immédiate côté organisateur).

### Phase 4 — Analytics et modules ML (Semaines 10–12)

- Back‑end (Synthia) : pipeline d'analyse de feedback (CamemBERT ou modèle francophone équivalent), module de recommandations simplifié (KNN ou heuristique), endpoints pour dashboard.
- Front‑end (Mathurin) : dashboard organisateur affichant sentiment, thèmes et indicateurs clés ; écran de feedback utilisateur.

Livrable de la phase : dashboard fonctionnel avec données test.

### Phase 5 — Finitions et déploiement (Semaines 13–16)

- Actions communes : intégration Stripe (version simplifiée), push notifications Firebase, tests et couverture minimale (objectif 70% pour la Definition of Done), déploiement staging, préparation de la démonstration finale.

Livrable final : démonstration complète et dépôt prêt pour soutenance.

## Simplifications acceptées pour le MVP

- Achat automatique de domaine : simuler l'attribution de sous‑domaines en démo.
- Messagerie interne et espace souvenir : fonctionnalités de niveau "Could Have", non prioritaires pour la soutenance.
- Modules ML complexes (GBM, OpenCV) : remplacer par règles heuristiques pour le MVP ; documenter clairement les améliorations futures.
- Authentifications sociales : reporter à version post‑MVP ; commencer par email + mot de passe.

## Consignes immédiates (à exécuter cette semaine)

1) Créez le dépôt Git commun et poussez une structure initiale claire : dossiers `/frontend` et `/backend`, README minimal et guide de contribution (branching, conventions de commit).
2) Définissez et documentez le contrat d'API pour les endpoints `register`, `login`, `get_profile` (format JSON exemple). Le contrat doit inclure schémas de requête/réponse et codes d'erreur attendus.

Ces deux éléments sont requis avant toute implémentation parallèle durable : sans dépôt partagé et sans contrat d'API, le front et le back se bloquent mutuellement.

## Nom du projet

"EventFlow" est acceptable, mais pour la soutenance je vous demande de proposer d'ici la fin de la semaine une alternative plus distinctive. Critères : mémorable, prononçable, et reflétant l'expérience que vous visez.

## Attentes pédagogiques

- Communication hebdomadaire : un court point écrit chaque vendredi (statut, blocages, tâches de la semaine suivante).
- Démo intermédiaire après la Phase 2 et une pré‑soutenance technique deux semaines avant la date officielle.
- Code lisible, commits atomiques et documentation minimale pour chaque composant majeur.

Si vous voulez, je peux relire votre proposition de nom, le README initial, et le contrat d'API dès que vous les poussez.

---


