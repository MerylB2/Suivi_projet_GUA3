
---

## LIVRABLES ATTENDUS — SUIVI DE PROGRESSION

Le suivi se fait en continu. À chaque point de jonction de phase, je m'attends à ce que vous soyez en mesure de me présenter les éléments suivants.

**Livrable 1 — Fin Phase 1 (Semaine 2)**
- Dépôt Git accessible avec structure `/frontend` et `/backend` séparés
- README clair : description du projet, instructions d'installation, liste des technologies
- Authentification fonctionnelle démontrable : inscription, connexion, token JWT retourné
- Au moins 3 commits significatifs par membre avec des messages descriptifs
- Nouveau nom de projet validé et soumis

**Livrable 2 — Fin Phase 2 (Semaine 6)**
- Création d'un événement de bout en bout démontrable en live devant moi
- Appel API Claude fonctionnel avec au moins 3 templates générés et affichés
- Mini-site rendu depuis une configuration JSON
- Documentation des endpoints API (Swagger/OpenAPI ou fichier Markdown)
- Diagramme de base de données à jour

**Livrable 3 — Fin Phase 3 (Semaine 9)**
- Système d'invitation fonctionnel avec lien unique
- Tableau de bord invités mis à jour en temps réel
- Formulaire RSVP intégré dans le mini-site
- Démonstration du WebSocket en live

**Livrable 4 — Fin Phase 4 (Semaine 12)**
- Dashboard analytique avec au moins l'analyse de sentiment fonctionnelle
- Rapport de couverture de tests (objectif minimum 70%)
- Bilan intermédiaire écrit que vous me remettez : ce qui est fait, ce qui reste, les difficultés rencontrées

**Livrable Final — Mai / Juin 2026**
- Application déployée sur un environnement staging accessible en ligne
- Code source complet sur Git avec historique propre
- Documentation technique complète
- Présentation orale avec démonstration live

---

## RÉPARTITION DES TÂCHES — CE QUE J'ATTENDS DE VOUS

C'est l'une des compétences que j'évalue le plus sérieusement dans un projet en binôme, et c'est aussi celle qui fait le plus souvent défaut. Je vous demande de travailler comme vous le feriez en entreprise, pas comme deux étudiants qui se partagent un devoir.

### Dans le code

**Règle fondamentale : vous ne touchez jamais au code de l'autre sans en parler.**

Synthia, tu es propriétaire du back-end. Mathurin, tu es propriétaire du front-end. Toute modification dans la zone de l'autre passe par une discussion, même brève. C'est une règle non négociable dans une équipe professionnelle.

Je vous demande d'adopter le workflow Git suivant dès le premier jour :

- `main` — version stable uniquement, vous ne poussez jamais directement dessus
- `develop` — branche d'intégration commune, vous mergez votre travail ici
- `feature/synthia-auth-jwt` — exemple de branche de fonctionnalité pour Synthia
- `feature/mathurin-event-form` — exemple de branche de fonctionnalité pour Mathurin

Chaque fonctionnalité = une branche. Quand c'est terminé, vous ouvrez une Pull Request vers `develop`. L'autre membre relit le code avant de merger. C'est exactement ce qui se fait dans toutes les équipes de développement, et je vérifierai que vous avez respecté ce processus dans votre historique Git lors de la soutenance.

Vos commits doivent suivre une convention lisible et précise :
- `feat: ajout du formulaire de création d'événement`
- `fix: correction de la validation du mot de passe`
- `docs: mise à jour du README`
- `test: ajout des tests sur l'endpoint login`

Un commit = une chose précise. Je ne veux pas voir de commits avec des messages vagues comme "modifications", "update" ou "wip". Ces messages ne veulent rien dire et trahissent un manque de rigueur professionnelle.

### Dans le workflow

**Le contrat d'API est votre outil de travail commun le plus important.** Avant que Mathurin commence un écran, Synthia lui fournit la spécification de l'endpoint correspondant : URL, méthode HTTP, format de la requête, format de la réponse, codes d'erreur possibles. Mathurin mocke cette réponse en local et développe l'écran sans attendre que le back soit prêt. Quand le back est prêt, vous branchez. Ce fonctionnement évite les blocages mutuels et c'est exactement ce que font les équipes full-stack en production.

**Je vous demande une réunion de synchronisation par semaine.** Pas longue — 30 minutes suffisent. Vous répondez à trois questions : qu'est-ce que j'ai fait cette semaine, qu'est-ce que je fais la semaine prochaine, est-ce que quelque chose me bloque. Vous me partagez un compte-rendu court de ces réunions, même sous forme de quelques lignes dans votre tableau de suivi.

**Je veux avoir accès à votre tableau de suivi partagé à tout moment.** Notion, Trello, ou un Google Sheet simple avec trois colonnes : À faire, En cours, Terminé. Chaque user story y est représentée. Je dois pouvoir consulter votre avancement réel sans attendre un livrable formel. C'est aussi votre meilleure protection en cas de question sur la contribution de chacun.

**La règle des 48 heures.** Si l'un de vous est bloqué sur quelque chose depuis plus de 48 heures, je veux en être informée. Rester bloqué en silence est la principale cause d'échec dans les projets en binôme. En entreprise, un développeur bloqué depuis deux jours sans rien signaler est un problème sérieux. Je préfère une question tôt qu'un retard tard.

### Ce que j'évaluerai dans votre répartition

Au-delà du code livré, voici ce que je regarderai de près lors de la soutenance. L'historique Git montre-t-il une contribution équilibrée et régulière des deux membres, ou des commits groupés en rafale la veille de la remise ? Chacun de vous est-il capable d'expliquer le code de l'autre et les choix architecturaux communs ? La documentation reflète-t-elle un travail coordonné ou deux morceaux assemblés à la dernière minute ?

Si l'un de vous ne peut pas répondre à mes questions sur la partie de l'autre lors de la soutenance, ce sera un signal fort que le travail n'a pas été réellement collaboratif, indépendamment de la qualité du code produit. Je vous préviens maintenant pour que vous organisiez votre travail en conséquence.