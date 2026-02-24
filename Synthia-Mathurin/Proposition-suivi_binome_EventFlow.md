
---

# SUIVI DE PROJET — EventFlow (Binôme)
**Synthia Donfack & Mathurin | Bachelor CDA | 2025–2026**

---

## PROPOSITION DE RÉPARTITION DES RÔLES

Avant de commencer à coder, il faut trancher cette question. Voici la répartition la plus naturelle compte tenu du projet :

**Synthia — Back-end + ML**
Le cahier des charges est le sien, elle maîtrise la vision métier. Django, les APIs, la base de données, les modules ML, Celery — c'est la colonne vertébrale du projet.

**Mathurin — Front-end + Intégration**
React Native/Expo, les composants, la gestion d'état, les appels API, le rendu des mini-sites depuis le JSON. Il fait le lien entre ce que le back produit et ce que l'utilisateur voit.

Les deux se retrouvent sur les points de jonction : définition des contrats d'API, tests d'intégration, déploiement.

---

## PLAN DE TRAVAIL RÉVISÉ EN BINÔME

La grande différence avec le plan solo : les phases 1 et 2 peuvent tourner **en parallèle**. Pendant que Synthia pose les fondations back-end, Mathurin construit les composants front-end. Ils se connectent à la fin de chaque phase.

---

### PHASE 1 — Fondations (Semaines 1-2)

**Synthia — Back-end**
- Initialiser le projet Django + PostgreSQL
- Modèles de données : User, Event, Invitation
- Authentification JWT (inscription, connexion, refresh token)
- Endpoints API : register, login, profil

**Mathurin — Front-end**
- Initialiser le projet React Native + Expo
- Structure de navigation (Expo Router)
- Composants de base : formulaires, cartes, boutons
- Écrans d'authentification (inscription, connexion)

**Point de jonction en fin de phase :** connexion front/back sur l'authentification fonctionnelle.

---

### PHASE 2 — Création d'événement + Templates IA (Semaines 3-6)

**Synthia — Back-end**
- Endpoints CRUD pour les événements
- Intégration API Claude : génération des 7 templates JSON
- Upload photos + traitement asynchrone Celery
- Système de sous-domaines dynamiques

**Mathurin — Front-end**
- Flow de création en 6 étapes (US-10)
- Composant de sélection de templates (swipe horizontal, aperçu)
- Moteur de rendu des mini-sites depuis le JSON généré
- Écran de publication

**Point de jonction en fin de phase :** création complète d'un événement de bout en bout, du formulaire jusqu'au mini-site publié.

---

### PHASE 3 — Gestion des invités (Semaines 7-9)

**Synthia — Back-end**
- Génération des liens uniques (256 bits d'entropie)
- Envoi SMS via Twilio
- WebSocket (Django Channels) pour les mises à jour temps réel
- Système RSVP avec questions personnalisées

**Mathurin — Front-end**
- Tableau de bord des invités temps réel (US-18)
- Formulaire RSVP intégré dans le mini-site
- Notifications in-app

**Point de jonction en fin de phase :** un invité reçoit un lien, confirme sa présence, et l'organisateur le voit en temps réel.

---

### PHASE 4 — Analytics + ML (Semaines 10-12)

**Synthia — Back-end + ML**
- Module analyse de sentiment CamemBERT sur les feedbacks
- Module recommandation de templates KNN
- Endpoints dashboard analytique

**Mathurin — Front-end**
- Dashboard organisateur avec graphiques (US-23)
- Écran de feedback post-événement (US-22)
- Rapport visuel : sentiment, thèmes, score global

**Point de jonction en fin de phase :** dashboard complet et fonctionnel avec données réelles.

---

### PHASE 5 — Finitions + Déploiement (Semaines 13-16)

Les deux ensemble :
- Abonnements Stripe (version simplifiée, sans achat de domaine automatique)
- Notifications push Firebase
- Tests — couverture minimale 70% pour valider la Définition of Done
- Déploiement en staging sur VPS
- Préparation de la démo pour Mai / juin 2026

---

## CE QU'ON SIMPLIFIE PAR RAPPORT AU CAHIER DES CHARGES

Pour rester faisables en 4 mois à deux, ces éléments sont mis de côté pour la présentation :

- L'achat automatique de domaine Namecheap (US-28) — simulé en démo
- La messagerie directe (US-30) — Could Have, pas critique
- L'espace souvenir (US-31) — Could Have, pas critique
- Les modules ML Gradient Boosting (prédiction de présence) et OpenCV/Colorthief (harmonisation couleurs) — remplacés par des règles simples pour le MVP
- La connexion sociale Google/Apple (US-02) — simplifiable à email/mot de passe pour commencer

---

## PROCHAINE ÉTAPE CONCRÈTE CETTE SEMAINE

Avant d'écrire une seule ligne de code, Synthia et Mathurin doivent faire deux choses ensemble :

**1. Créer le dépôt Git commun** avec une structure de dossiers séparant clairement `/frontend` et `/backend`, conformément au Chapitre 1 (séparation des préoccupations).

**2. Définir le contrat d'API** des 3 premiers endpoints (register, login, get_profile) sous forme de fichier JSON ou document partagé, pour que Mathurin puisse mocker les réponses côté front pendant que Synthia les implémente côté back.

Ces deux actions permettent de travailler en parallèle dès le premier jour sans se bloquer mutuellement.

---

**3. Revoir le nom du projet**

"EventFlow" est un nom propre et bien construit, mais il sonne comme un nom généré par une IA — trop lisse, trop générique. Pour un projet de fin d'études présenté devant un jury, un nom plus personnel ou ancré dans une intention précise donne une meilleure impression et montre que le projet vient vraiment de vous.

Quelques pistes pour trouver un meilleur nom : partir d'un mot dans votre langue, d'une métaphore liée aux événements, d'une contraction de deux mots qui ont du sens pour vous, ou d'un nom qui raconte quelque chose sur l'expérience que vous voulez créer. Le nom doit être mémorable, prononçable, et refléter votre identité en tant qu'auteurs du projet.

C'est un détail qui compte plus qu'on ne le croit lors d'une soutenance.
Soumettez-moi une proposition avant la fin de la semaine.
