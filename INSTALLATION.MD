Installer le skill « Conseiller produit Buffet-Plus » dans Claude
Ce guide explique comment ajouter le skill à ton compte Claude pour qu'il se déclenche
automatiquement quand tu décris un brief client.
Dépôt public : https://github.com/cyrildantin-maker/buffet-plus-conseil-produit
---
Prérequis
Un compte Claude Free, Pro, Max, Team ou Enterprise (les skills sont disponibles
sur tous les plans).
Code Execution and File Creation activé — c'est indispensable, le skill ne
fonctionne pas sans. On l'active à l'étape 1.
---
Étape 1 — Activer l'exécution de code
Va dans Settings (Paramètres) → Capabilities (Capacités).
Lien direct : https://claude.ai/settings/capabilities
Vérifie que Code execution and file creation est bien activé (interrupteur sur ON).
> Sur un compte Team ou Enterprise, cette option peut devoir être activée au niveau de
> l'organisation par un administrateur (Organization settings → Skills). Si tu ne la vois
> pas, c'est le point à vérifier avec l'admin.
---
Étape 2 — Récupérer le skill au bon format
Claude attend un dossier compressé en .zip dont la racine est le dossier du skill
lui-même (pas les fichiers en vrac, pas un dossier qui en contient un autre).
Méthode A — Télécharger depuis GitHub (la plus simple)
Ouvre le dépôt : https://github.com/cyrildantin-maker/buffet-plus-conseil-produit
Clique sur le bouton vert « Code » puis « Download ZIP ».
GitHub télécharge un fichier nommé quelque chose comme
`buffet-plus-conseil-produit-main.zip`.
Important — corriger la structure du zip :
Décompresse le fichier téléchargé. Tu obtiens un dossier
`buffet-plus-conseil-produit-main`.
Renomme ce dossier en `buffet-plus-conseil-produit` (retire le `-main`).
Vérifie qu'à l'intérieur, tu as directement `SKILL.md`, `README.md` et le dossier
`data/` — pas un sous-dossier intermédiaire.
Recompresse ce dossier en `.zip`.
> Pourquoi cette manipulation : GitHub ajoute toujours un suffixe `-main` et une couche
> de dossier. Claude, lui, veut le dossier du skill comme racine du zip, avec un nom qui
> correspond au skill. Si le zip est mal structuré, l'upload échoue silencieusement.
Méthode B — Pointer directement vers le dépôt Git
Depuis fin 2025, Claude accepte aussi un lien vers un dépôt Git contenant un `SKILL.md`.
Si cette option est proposée dans ton interface au moment de l'ajout (étape 3), tu peux
coller directement l'URL du dépôt :
```
https://github.com/cyrildantin-maker/buffet-plus-conseil-produit
```
et sauter la manipulation du zip. Selon la version de l'interface, cette option n'est pas
toujours visible — si tu ne la vois pas, utilise la méthode A.
---
Étape 3 — Ajouter le skill dans Claude
Va dans Customize (Personnaliser) → Skills.
Selon l'interface, le chemin peut être Settings → Capabilities → Skills.
Clique sur le bouton « + » puis « Create skill » (ou « Upload skill »).
Charge le fichier .zip préparé à l'étape 2 (ou colle l'URL Git si la méthode B est
disponible).
Une fois le skill ajouté, active-le avec l'interrupteur (les skills uploadés sont
privés à ton compte, désactivés par défaut).
---
Étape 4 — Tester
Dans une nouvelle conversation, écris un brief client, par exemple :
> Aide-moi à conseiller un client qui ouvre une brasserie néo-chic à Nice, 50 couverts,
> service à table, salades et grillades.
Le skill doit se déclencher automatiquement et proposer une recommandation de gammes.
Tu peux aussi l'invoquer explicitement :
> Utilise le skill de conseil produit Buffet-Plus pour ce brief.
Et vérifier qu'il est bien chargé en demandant :
> Quels skills sont disponibles ?
---
Partager le skill avec un collaborateur
Deux options selon ton plan :
Plans Team / Enterprise : dans Customize → Skills, ouvre le skill et utilise
Share pour le partager avec des personnes précises (par email) ou toute
l'organisation. Le skill apparaît chez eux (désactivé jusqu'à ce qu'ils l'activent),
et tes mises à jour leur sont automatiquement poussées.
Tous les plans : envoie-leur simplement le fichier `.zip`, ou le lien du dépôt
GitHub. Chacun l'ajoute via ses propres réglages Skills en suivant ce même tutoriel.
---
En cas de problème
Le skill ne se déclenche pas — vérifie qu'il est bien activé (interrupteur ON) et que
Code Execution est activé. Le déclenchement dépend aussi de la description du skill : elle
est conçue pour réagir aux mots comme « brief client », « recommandation APS »,
« quelle série pour… ». Tu peux toujours l'invoquer explicitement.
L'upload échoue — c'est presque toujours la structure du zip. Reprends l'étape 2 :
le dossier du skill doit être la racine du zip, avec `SKILL.md` directement dedans.
« Skill not found » dans Cowork ou une session cloud — ces sessions chargent les
skills activés sur ton compte claude.ai. Assure-toi que le skill est activé dans les
réglages, pas seulement présent localement.
---
Skill édité par Buffet-Plus — https://www.buffet-plus.com
