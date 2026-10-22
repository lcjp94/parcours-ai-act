# Parcours AI Act — version locale

Application d'auto-formation à l'AI Act européen (règlement (UE) 2024/1689, modifié par le règlement Omnibus (UE) 2026/1744). Contenu à jour au 21 octobre 2026.

## Lancer

Ouvrez `parcours-ai-act.html` dans un navigateur récent. Aucun serveur ni installation n'est nécessaire. Une connexion internet sert uniquement à charger les polices (Google Fonts) ; sans connexion, l'application fonctionne avec les polices système.

Pour la diffuser à une équipe : déposez le fichier sur un intranet, un SharePoint ou tout hébergement statique (GitHub Pages, Azure Static Web Apps…).

## Fonctionnement

- **Deux profils** : Cadre utilisateur (6 modules, questions de niveau 1) et Responsable conformité / DSI (10 modules, niveaux 1 et 2, approfondissements, livrables portfolio).
- **Test de positionnement** : une question par module ; une bonne réponse marque le module « pré-acquis » (accessible directement, mais à valider par son quiz).
- **Déblocage progressif** : un module s'ouvre quand tous les précédents sont validés (quiz ≥ 75 %) ou pré-acquis.
- **Révisions ciblées** : chaque erreur est ajoutée à une file ; une question en sort dès qu'elle est réussie.
- **Qualifier un cas** : questionnaire qui pré-qualifie un cas d'usage (interdit, haut risque Annexe I/III, transparence, minimal), liste les obligations et dates, et produit une synthèse à copier.

## Données

La progression est stockée dans le `localStorage` du navigateur. Elle n'est envoyée nulle part. Onglet **Profil** : export / import par copier-coller pour changer d'appareil.

Limite pour un usage en entreprise : il n'y a pas de suivi centralisé des apprenants. Pour cela, il faudrait ajouter un back-end (authentification + base de données) ou un LMS (export SCORM).

## Modifier le contenu

Tout le contenu est dans le tableau `MODULES` en tête du `<script>` :

- `lessons` : sections (`lvl: 2` = réservé au profil responsable)
- `quiz` : questions (`lvl: 1` = tous profils, `lvl: 2` = responsable ; `a` = index de la bonne réponse)
- `PLACEMENT` : questions du test de positionnement
- `PROFILES.paths` : modules de chaque parcours

Changer la clé `KEY` (ex. `aiact-parcours-v2`) remet à zéro la progression des utilisateurs après une refonte du contenu.

## Avertissement

Contenu pédagogique, pas un avis juridique. Vérifiez le texte consolidé sur EUR-Lex. Les mentions « à vérifier » dans l'application signalent les points incertains ou évolutifs.
