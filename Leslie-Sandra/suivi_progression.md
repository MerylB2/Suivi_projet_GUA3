# SUIVI PROGRESSION & LIVRABLES — TaskFlow
**Leslie & Sandra | Licence Pro Full Stack | 2025–2026**

---

## Livrables Attendus

**Livrable 0 — Avant de commencer à coder (Cette semaine)**
- Un seul dépôt Git commun créé, accessible par les deux membres et par moi
- Choix du back-end tranché et documenté : Node.js/Express ou Django, pas les deux
- Répartition des rôles écrite dans le README
- Document de conception fusionné et corrigé remis en format Markdown (pas un notebook Jupyter)

**Livrable 1 — Fin Phase 1 (Semaine 2)**
- Structure de projet en place : `/frontend` et `/backend` séparés
- README complet : description, stack finale, instructions d'installation, noms des deux contributrices
- Au moins 3 commits significatifs par membre avec messages descriptifs
- Authentification fonctionnelle : inscription, connexion, token JWT retourné

**Livrable 2 — Fin Phase 2 (Semaine 5)**
- CRUD complet sur les tâches démontrable en live devant moi
- Filtrage par statut et recherche par mot-clé fonctionnels
- Composants React opérationnels : TaskForm, TaskCard, TaskList
- Validation côté serveur sur tous les endpoints

**Livrable 3 — Fin Phase 3 (Semaine 8)**
- Application complète déployée ou fonctionnelle en local avec démo stable
- Tests sur les endpoints principaux
- Rapport de couverture de tests
- Bilan écrit remis : ce qui fonctionne, ce qui reste, les difficultés rencontrées

**Livrable Final**
- Code source propre sur Git avec historique lisible
- Documentation technique complète et à jour
- Présentation orale avec démonstration live sans bugs

---

## Répartition des Tâches — Ce que J'attends de Vous

### Dans le code

**Leslie, tu es propriétaire du frontend et de la documentation. Sandra, tu es propriétaire du backend et de l'authentification.** Toute modification dans la zone de l'autre se discute avant d'être faite.

Workflow Git obligatoire dès le premier jour :

- `main` — version stable, on ne pousse jamais directement dessus
- `develop` — branche d'intégration commune
- `feature/leslie-tasklist-component` — exemple de branche pour Leslie
- `feature/sandra-auth-jwt` — exemple de branche pour Sandra

Chaque fonctionnalité = une branche. Pull Request vers `develop`. L'autre membre relit avant de merger.

Convention de commits :
- `feat: composant TaskCard avec badge de priorité`
- `fix: correction de la validation du titre vide`
- `docs: mise à jour des endpoints dans le README`
- `test: test de l'endpoint POST /tasks`

Je ne veux pas voir de commits avec des messages comme "modif", "update" ou "correction". Ces messages ne racontent rien sur ce que vous avez fait.

### Dans le workflow

**Le contrat d'API est la première chose à produire ensemble.**
Avant que Leslie commence les composants React, Sandra lui fournit le format exact de chaque réponse API : structure JSON retournée, codes HTTP, messages d'erreur. Leslie mocke ces réponses et développe le frontend sans attendre. Quand le backend est prêt, on branche. Ce fonctionnement vous permet de travailler en parallèle sans vous bloquer mutuellement.

**Une réunion de synchronisation par semaine.**
30 minutes, trois questions : qu'est-ce que j'ai fait, qu'est-ce que je fais la semaine prochaine, est-ce que quelque chose me bloque. Compte-rendu court partagé avec moi.

**Tableau de suivi partagé accessible à tout moment.**
Trello, Notion ou Google Sheet. Trois colonnes : À faire, En cours, Terminé. Je dois pouvoir y accéder sans vous le demander.

**La règle des 48 heures.**
Si l'une de vous est bloquée depuis plus de deux jours, je veux en être informée. Rester bloquée en silence est la principale cause d'échec dans un projet en binôme.

### Ce que J'évaluerai

L'historique Git montre-t-il une contribution régulière et équilibrée des deux membres ? Chacune peut-elle expliquer le code de l'autre lors de la présentation ? La documentation reflète-t-elle un travail coordonné ou deux morceaux assemblés à la dernière minute ?

---

## Corrections Prioritaires à Apporter Maintenant

Ces points doivent être corrigés avant de soumettre le document de conception final.

**Pour Leslie :**
- Corriger la faute de frappe `created_ad` en `created_at` dans la table tasks
- Trancher entre MySQL et PostgreSQL — choisir PostgreSQL et le justifier
- Ajouter l'authentification dans les besoins fonctionnels et les endpoints
- Convertir le notebook Jupyter en fichier Markdown propre
- Étoffer la conclusion

**Pour Sandra :**
- Compléter la section modélisation des données avec la table users et la table tasks
- Compléter la section endpoints API
- Compléter la section structure du projet
- Compléter la section documentation de conception
- Remplacer Flask-Login par JWT — Flask et Django sont deux frameworks incompatibles, on ne les mélange pas
- Remettre le contenu dans une cellule Markdown au lieu d'une cellule code dans le notebook
- Convertir le notebook Jupyter en fichier Markdown propre

**Pour les deux :**
- Produire un seul document de conception fusionné qui intègre le meilleur des deux propositions
- Ce document doit être un fichier Markdown ou PDF, pas un notebook Jupyter
- Y ajouter la répartition des rôles et le workflow Git

---

## Prochaines Étapes Immédiates

**1. Créer le dépôt Git commun**
Une seule structure, `/frontend` et `/backend` séparés. README avec les deux noms, la stack choisie, et les instructions d'installation.

**2. Définir le contrat d'API**
Sandra produit un fichier `api-contract.md` dans le dépôt avec le format JSON de chaque réponse. Leslie attend ce fichier pour commencer les composants.

**3. Trancher le back-end**
Node.js/Express est recommandé pour rester aligné sur le Chapitre 3 du cours. Si vous choisissez Django, argumentez ce choix dans le document de conception.

**4. Fusionner les deux documents de conception en un seul**
C'est votre premier livrable commun. Il doit refléter une décision d'équipe sur chaque point, pas deux propositions côte à côte.

**5. Revoir le nom du projet**
"TaskFlow AI" sonne comme un nom généré par une IA. Pour un dossier RNCP et une soutenance, un nom qui raconte votre histoire et votre démarche pèse davantage. 

Quelques pistes pour trouver un meilleur nom : partir d'un mot dans votre langue, d'une métaphore liée aux événements, d'une contraction de deux mots qui ont du sens pour vous, ou d'un nom qui raconte quelque chose sur l'expérience que vous voulez créer. Le nom doit être mémorable, prononçable, et refléter votre identité en tant qu'auteurs du projet.

C'est un détail qui compte plus qu'on ne le croit lors d'une soutenance.
Soumettez-moi une proposition avant la fin de la semaine.