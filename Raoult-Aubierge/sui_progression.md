# SUIVI PROGRESSION & LIVRABLES — DevFlow AI
**Raoult & Aubierge | Bachelor CDA | 2025–2026**

---

## Livrables Attendus

**Livrable 1 — Fin Phase 1 (Semaine 4)**
- Dépôt Git accessible avec structure claire et README en place
- Authentification fonctionnelle démontrable (NextAuth.js)
- Dashboard basique avec CRUD projets opérationnel
- Contrat d'API entre les 4 agents documenté et versé dans le dépôt
- Au moins 3 commits significatifs par membre par semaine
- Nouveau nom de projet soumis et validé par moi

**Livrable 2 — Fin Phase 2 (Semaine 8)**
- Pipeline des 4 agents fonctionnel de bout en bout, même sur un exemple simple
- Documentation des formats JSON échangés entre chaque agent
- Score de fidélité affiché, même approximatif
- Démonstration live devant moi : une URL Figma entre, du code Next.js sort

**Livrable 3 — Fin Phase 3 (Semaine 12)**
- MVP complet déployé sur Vercel, accessible en ligne
- Rapport de couverture de tests
- Bilan intermédiaire écrit remis : ce qui fonctionne, ce qui reste à faire, les difficultés rencontrées

**Livrable Final — Juin 2025**
- Application déployée et stable sur Vercel
- Dossier RNCP complet remis dans les délais
- Code source propre sur Git avec historique lisible
- Présentation orale avec démo live sans bugs
- Deux designs Figma de secours préparés et testés la veille

---

## Répartition des Tâches — Ce que J'attends de Vous

### Dans le code

**Raoult, tu es propriétaire des Agents 1 et 2 et de l'interface utilisateur. Aubierge, tu es propriétaire du back-end, de la base de données et des Agents 3 et 4.** Toute modification dans la zone de l'autre passe par une discussion. Ce n'est pas une règle rigide, c'est une protection pour tous les deux.

Je vous demande d'adopter le workflow Git suivant dès le premier jour :

- `main` — version stable uniquement, vous ne poussez jamais directement dessus
- `develop` — branche d'intégration commune
- `feature/raoult-agent-parser` — exemple de branche pour Raoult
- `feature/aubierge-auth-nextauth` — exemple de branche pour Aubierge

Chaque fonctionnalité = une branche. Pull Request vers `develop`. L'autre membre relit avant de merger. Je vérifierai cet historique lors de l'évaluation.

Convention de commits obligatoire :
- `feat: agent 1 - extraction couleurs depuis API Figma`
- `fix: correction du token NextAuth expiré`
- `docs: documentation format JSON Agent 2`
- `test: validation score fidélité Agent 4`

Un commit vague comme "update" ou "fix bug" ne me dit rien sur ce que vous avez fait. Je veux des messages qui racontent l'histoire du projet.

### Dans le workflow

**Le contrat d'API entre les agents est votre outil de travail le plus important.**
Avant de coder quoi que ce soit, définissez ensemble le format JSON exact que chaque agent reçoit et produit. Aubierge ne peut pas coder l'Agent 3 sans savoir ce que l'Agent 2 de Raoult lui envoie. Ce document de contrat doit être dans votre dépôt Git dès la semaine 1. C'est non négociable.

**Une réunion de synchronisation par semaine, compte-rendu court partagé avec moi.**
30 minutes, trois questions : qu'est-ce que j'ai fait, qu'est-ce que je fais la semaine prochaine, qu'est-ce qui me bloque. Je dois pouvoir lire ce compte-rendu.

**La règle des 48 heures.**
Si l'un de vous est bloqué depuis plus de deux jours, je veux en être informée. Raoult, qui apprend Next.js en même temps qu'il développe, sera particulièrement exposé à ce risque — surtout les premières semaines. Ce n'est pas une faiblesse de demander de l'aide, c'est une compétence professionnelle.

**Tableau de suivi partagé accessible à tout moment.**
Trello, Notion, ou Google Sheet. Je dois pouvoir y accéder sans vous demander. C'est aussi votre meilleure protection en cas de question sur la contribution de chacun.

### Ce que J'évaluerai dans Votre Répartition

Je regarderai si l'historique Git montre une contribution régulière et équilibrée des deux membres, ou si les commits arrivent en rafale la veille des livrables. Je vérifierai que chacun de vous peut expliquer le code de l'autre lors de la soutenance. Et j'évaluerai si votre dossier RNCP et votre présentation racontent une histoire cohérente écrite à deux, pas deux monologues assemblés au dernier moment.

Raoult, ton parcours de designer qui devient développeur est un atout narratif exceptionnel pour la soutenance RNCP. C'est précisément le profil que ce titre valorise. Ne l'utilise pas seulement dans l'introduction — montre comment cette double compétence se reflète concrètement dans les choix techniques du projet.

---

## Prochaines Étapes Immédiates

**1. Créer le dépôt Git commun**
Structure claire dès le départ. README avec description, stack, instructions d'installation, et noms des deux contributeurs.

**2. Rédiger le contrat d'API entre les 4 agents**
C'est la première tâche commune, avant toute ligne de code. Le format JSON de sortie de chaque agent doit être défini et versé dans le dépôt. Sans ce document, Raoult et Aubierge ne peuvent pas travailler en parallèle.

**3. Préparer deux designs Figma de démo**
Simples, sur votre propre compte Figma, accessibles avec vos tokens. Testés dès que l'Agent 1 est opérationnel. Ne jamais dépendre d'un design externe pour une démo en live.

**4. Revoir le nom du projet**
"DevFlow AI" sonne comme un nom généré par une IA. Pour un dossier RNCP et une soutenance, un nom qui raconte votre histoire et votre démarche pèse davantage. Soumettez-moi une proposition avant la fin de la semaine.