# SUIVI DE PROJET — EventFlow
**Donfack Synthia Calorine**

---

## 1. RÉSUMÉ DU PROJET

EventFlow est une plateforme web et mobile de gestion d'événements qui permet à n'importe qui (particulier ou pro) de créer un mini-site d'événement personnalisé grâce à l'IA, gérer ses invités avec des liens uniques, et obtenir un rapport analytique automatique après l'événement. Le tout sans compétences techniques.

**Stack :** React Native (Expo) + Django REST Framework + PostgreSQL + Redis + Claude API + modules ML Python.

**Deadline :** Juin 2025 — soit environ 4 mois de développement effectif restants.

---

## 2. PROBLÈMES IDENTIFIÉS

**Problème 1 — Le projet est trop grand pour 4 mois en solo.**
471 points de complexité sur 24 semaines, c'est le rythme d'une équipe de 2-3 développeurs. En solo, c'est un risque réel de ne rien finir correctement plutôt que de tout finir à moitié.

**Problème 2 — Décalage technologique avec le cours.**
Le cours (Chap. 3) enseigne Node.js/Express comme back-end principal. EventFlow utilise Django. C'est justifiable techniquement (Python + ML = cohérent), mais cela crée un écart avec ce qui est attendu et enseigné en cours. Il faut anticiper cette question lors de la présentation.

**Problème 3 — 4 modules ML intégrés dès le MVP.**
CamemBERT, KNN, Gradient Boosting, OpenCV/Colorthief... chacun est un projet à part entière. Les intégrer tous au MVP en 4 mois est très ambitieux.

**Problème 4 — Dépendances tierces nombreuses et risquées.**
Stripe + Twilio + Namecheap API + Firebase + Cloudflare R2 + Let's Encrypt + Claude API = beaucoup de points de défaillance potentiels. Si une API change ou est indisponible pendant les tests, le développement est bloqué.

**Problème 5 — L'achat automatique de domaine (US-28) est hors-sujet pour un projet académique.**
C'est une fonctionnalité impressionnante sur le papier, mais complexe à démontrer et peu évaluée dans le cadre du cours.

---

## 3. SUGGESTIONS ET POINTS DE CORRECTION

**Simplifier le scope ML :** Pour la présentation, garder seulement 2 modules ML au lieu de 4. Priorité à l'analyse de sentiment (CamemBERT — valeur visible dans le dashboard) et la recommandation de templates (coeur de la proposition de valeur). La prédiction de présence et l'harmonisation des couleurs peuvent être simulées avec des règles simples pour le MVP.

**Simuler l'achat de domaine :** Pour la démo, un mock ou une démonstration fictive suffit. Ne pas dépendre de l'API Namecheap en live.

**React Native vers React Web d'abord :** Le cours évalue React (Chap. 2), pas React Native. S'assurer que la version web Expo fonctionne parfaitement. La version mobile est un bonus.

**Réduire les user stories Must Have :** 16 user stories Must Have toutes à livrer, c'est trop. On peut en reclasser 4 ou 5 en Should Have sans impacter la démonstration — notamment la messagerie, l'espace souvenir, l'achat de domaine.

**Corriger l'alignement cours/projet :** Le Chapitre 3 enseigne la validation côté serveur, les controllers, l'architecture MVC, JWT. EventFlow couvre tout ça avec Django — il faut le mentionner explicitement dans la présentation avec les termes du cours.

---

## 4. PLAN DE TRAVAIL PAR PRIORITÉ ET FAISABILITÉ

### PHASE 1 — Fondations (Semaines 1-3) — CRITIQUE
Ce sont les bases sans lesquelles rien d'autre ne fonctionne. Directement lié au **Chapitre 1** (architecture en couches) et **Chapitre 3** (back-end, JWT, CRUD).

- Initialiser le projet Django + React Native/Expo + PostgreSQL
- Authentification complète (US-01, US-03) avec JWT — bcrypt, access token, refresh token
- Profil utilisateur (US-04)
- CI/CD basique + Git structuré

### PHASE 2 — Création d'événement + Templates IA (Semaines 4-7) — COEUR DU PROJET
C'est la fonctionnalité différenciante. Lié au **Chapitre 2** (composants React, gestion d'état) et **Chapitre 3** (API REST, logique métier).

- Flow de création en étapes (US-10) — les 6 étapes
- Upload et traitement photos asynchrone (US-12) — Celery
- Appel API Claude + génération de 7 templates JSON (US-11)
- Moteur de rendu des mini-sites depuis JSON
- Publication public/privé (US-14, US-15)

### PHASE 3 — Gestion des invités (Semaines 8-10) — IMPORTANT
Lié au **Chapitre 3** (WebSocket, gestion des données temps réel).

- Invitations membres et SMS (US-16, US-17)
- Tableau de bord invités temps réel via WebSocket (US-18)
- Système RSVP (US-19)

### PHASE 4 — Analytics + ML (Semaines 11-13) — VALEUR AJOUTÉE
Lié au **Chapitre 1** (séparation des couches, pipeline de données).

- Analyse de sentiment CamemBERT sur les feedbacks (US-22, US-23)
- Recommandation de templates KNN (US-11 — modèle ML)
- Dashboard analytique organisateur

### PHASE 5 — Monétisation + Finitions (Semaines 14-16) — SI LE TEMPS LE PERMET

- Stripe abonnements (US-27) — sans l'achat de domaine automatique
- Notifications (US-29)
- Tests + déploiement staging

---

## 5. LIAISON AVEC LES CHAPITRES DU COURS

**Chapitre 1 — Architecture Full Stack :** EventFlow applique exactement la séparation en 3 couches enseignée. React Native = couche présentation, Django REST = couche métier/logique, PostgreSQL + Redis = couche persistance. Le flux de données respecte le schéma Utilisateur vers Front vers Back vers BDD et retour. A mentionner explicitement lors de la soutenance.

**Chapitre 2 — Front-end Avancé :** Les composants EventFlow correspondent aux exercices du cours — EventForm (création d'événement = formulaire), EventCard (carte dans le fil d'actualité), EventList (fil avec filtres et chargement infini). La gestion d'état avec Zustand remplace useState/useContext mais le principe est le même. L'accessibilité RGAA et le design responsive sont couverts par Expo Web.

**Chapitre 3 — Back-end Avancé :** Django REST Framework couvre tout ce que le chapitre enseigne — API REST avec controllers (views DRF), validation serveur, authentification JWT, gestion des erreurs centralisée, architecture MVC. Le fait d'utiliser Python/Django plutôt que Node.js/Express est une décision justifiée par l'intégration ML, mais les principes SOLID et OWASP s'appliquent identiquement.

**Mini-Projet 2 :** Les 3 composants minimum requis sont clairement identifiables dans EventFlow — EventForm, EventCard, EventList. La logique métier CRUD est dans les services Django. L'architecture est en couches. Toutes les cases de la grille d'évaluation sont cochées.

---

En résumé, le projet est excellent sur le fond, ambitieux sur la forme. L'enjeu des prochaines semaines est de résister à la tentation de tout faire et de livrer un MVP solide sur les phases 1, 2 et 3. Un projet qui fonctionne à 70% vaut mieux qu'un projet conçu à 100% mais non démontrable.