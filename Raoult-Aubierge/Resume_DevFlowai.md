# RESUME — DevFlow AI
**Raoult & Aubierge | Bachelor CDA | 2025–2026**

---

## Le Projet

DevFlow AI est une plateforme SaaS qui transforme automatiquement des designs Figma en code Next.js production-ready grâce à un pipeline de 4 agents IA. L'utilisateur colle une URL Figma, clique sur "Generate", et obtient du code React/Next.js prêt pour la production avec un score de fidélité visuelle supérieur à 90%.

**Stack :** Next.js 15, TypeScript, TailwindCSS, shadcn/ui, Prisma, PostgreSQL (Supabase), Claude Sonnet 4, Vercel AI SDK, NextAuth.js, Playwright, Zustand, Vercel

**Atout majeur du binôme :** Raoult est designer professionnel avec 3 ans d'expérience et a déjà construit un agent IA Figma vers HTML/CSS via n8n + OpenAI. Ce n'est pas un projet théorique — il y a une vraie base technique existante.

**Deadline :** Soutenance RNCP Juin 2025 — 16 semaines à partir de février 2025.

---

## Les 4 Agents IA

- **Agent 1 — Parser :** extrait les frames, couleurs, typographie et assets depuis l'API Figma REST
- **Agent 2 — Analyzer :** analyse le design system avec Claude Vision pour identifier composants et tokens
- **Agent 3 — Generator :** génère le code Next.js/React depuis le design system via Claude Sonnet 4
- **Agent 4 — Validator :** compare le rendu généré avec le design original et calcule un score de fidélité

---

## Problèmes Identifiés

**Le nom "DevFlow AI" sonne comme un nom généré par une IA.**
Devant un jury RNCP, un nom plus personnel ou ancré dans votre démarche créera une meilleure impression et montrera que le projet vous appartient vraiment. A revoir avant tout dépôt officiel.

**La roadmap est pensée pour une personne, pas pour un binôme.**
Le document est rédigé entièrement à la première personne du singulier. La répartition des tâches entre Raoult et Aubierge n'est nulle part définie. C'est un risque sérieux à corriger immédiatement.

**L'Agent 4 (Validator avec Playwright) est trop ambitieux pour le MVP.**
Lancer un navigateur headless, capturer un screenshot, le comparer via Claude Vision et calculer un score de fidélité est une fonctionnalité complexe qui peut mobiliser plusieurs semaines à elle seule. Si elle ne fonctionne pas en démo, tout le discours sur les "90% de fidélité" s'effondre.

**Dépendance critique à l'API Figma.**
Toute la valeur du produit repose sur l'accès à l'API Figma REST. Si un token expire, si Figma modifie son API, ou si le design est privé, l'Agent 1 tombe et tout le pipeline s'arrête. Il n'y a pas de plan de secours documenté.

**Raoult apprend Next.js en même temps qu'il développe.**
C'est courageux et cohérent avec la méthode "learning by doing", mais les premières semaines seront plus lentes. Il ne faut pas sous-estimer ce temps d'apprentissage dans le planning.

**Décalage avec le cours.**
Le cours enseigne une architecture front/back/BDD séparée (Chapitre 1) avec React (Chapitre 2) et Node.js/Express (Chapitre 3). Next.js fusionne ces couches. C'est justifiable techniquement mais il faudra l'expliquer clairement lors de la soutenance.

---

## Suggestions et Points de Correction

- Simplifier l'Agent 4 pour le MVP : calculer le score de fidélité sur les couleurs dominantes et la structure de blocs, sans Playwright. La validation pixel-perfect est documentée comme évolution Phase 2 — ce qui est déjà prévu dans la roadmap.
- Préparer deux designs Figma personnels et simples pour la démo, hébergés sur votre propre compte Figma, testés la veille. Ne jamais utiliser un lien Figma externe en live.
- Définir le contrat d'API entre les agents dès la semaine 1 — le format JSON exact que chaque agent reçoit et produit. Aubierge ne peut pas coder sans ce document.
- Lors de la soutenance, montrer explicitement que vous maîtrisez la séparation des couches du Chapitre 1 malgré l'utilisation de Next.js : API Routes = back-end, Prisma = couche données, composants React = couche présentation.
- Revoir le nom du projet avant toute communication officielle.

---

## Proposition de Répartition des Rôles

**Raoult — Agents 1 et 2 + Interface utilisateur**
Son terrain naturel : il connaît l'API Figma, il maîtrise le design system, il a l'oeil pour l'UI. Parser, Analyzer, composants visuels du dashboard, landing page.

**Aubierge — Back-end + Agents 3 et 4 + Infrastructure**
Base de données Prisma, authentification NextAuth.js, API Routes, Agent Generator (Claude Sonnet 4), Agent Validator (version simplifiée MVP), CI/CD.

Les deux se retrouvent sur les points de jonction : définition des contrats d'API entre agents, tests d'intégration, déploiement Vercel.

---

## Plan de Travail par Phase

**Phase 1 — Fondations (Semaines 1-4)**
Raoult : Next.js Learn semaine 1 en priorité, puis composants UI dashboard (ProjectCard, GenerationViewer, StatusBadge), design du dashboard sur Figma.
Aubierge : initialisation projet Next.js + TypeScript, modèles Prisma (User, Project, Generation), authentification NextAuth.js, API Routes CRUD projets.
Point de jonction : un utilisateur peut se connecter, créer un projet, le voir dans le dashboard.

**Phase 2 — Pipeline des Agents IA (Semaines 5-8)**
Raoult : Agent 1 (extraction depuis API Figma) + Agent 2 (analyse design system avec Claude Vision).
Aubierge : Agent 3 (génération code Next.js avec Claude Sonnet 4 + Vercel AI SDK) + Agent 4 simplifié (score de fidélité basique).
Point de jonction : pipeline complet de bout en bout — une URL Figma entre, du code Next.js sort.

**Phase 3 — Interface et Polish (Semaines 9-12)**
Les deux ensemble, Raoult en lead sur l'UI : dashboard complet, preview live du code généré, affichage temps réel de la progression des agents, versioning des projets, tests E2E, CI/CD GitHub Actions, Lighthouse 90+.

**Phase 4 — Finalisation RNCP (Semaines 13-16)**
Landing page marketing (Raoult en lead), dossier technique RNCP rédigé et relu à deux, 10 répétitions minimum de la présentation, deux designs Figma de démo préparés et testés, déploiement stable sur Vercel.

---

## Liaison avec les Chapitres du Cours

**Chapitre 1 — Architecture Full Stack**
Next.js fusionne front-end et back-end dans un seul projet, ce qui peut sembler en contradiction avec la séparation en couches enseignée. Les couches existent, elles sont organisées différemment : composants React = couche présentation, API Routes = couche logique métier, Prisma + PostgreSQL = couche persistance. Ce mapping doit être expliqué explicitement en soutenance.

**Chapitre 2 — Front-end Avancé**
DevFlow AI est un cas d'application complet de ce que ce chapitre enseigne : composants React réutilisables (ProjectCard, AgentStatusBar, CodePreview), gestion d'état avec Zustand, cycle de vie avec useEffect pour le streaming des agents, props et state. Pour le Mini-Projet 2, les 3 composants requis sont directement identifiables : ProjectForm, ProjectCard, ProjectList.

**Chapitre 3 — Back-end Avancé**
Les API Routes de Next.js jouent exactement le rôle du back-end du Chapitre 3 : validation des entrées avec Zod, authentification JWT via NextAuth.js, logique métier dans les routes, gestion des erreurs centralisée, principes SOLID. L'utilisation de Next.js plutôt que Node.js/Express est un choix architectural délibéré à argumenter, pas une méconnaissance du cours.