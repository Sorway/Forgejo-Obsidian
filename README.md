# Obsidian — thème sombre pour Forgejo

Noir profond légèrement bleuté, accent mauve grisé et désaturé, surfaces discrètes et focus clavier visibles. Sans police distante, JavaScript ou modification des templates. Le thème hérite de `forgejo-dark` pour conserver la coloration du code, les diffs et les couleurs des statuts.

## Installation

1. Copier `theme-obsidian.css` dans `$FORGEJO_CUSTOM/public/assets/css/` sur le serveur. Le dossier personnalisé se trouve dans Administration du site → Configuration, ou avec `forgejo help`.
2. Dans la section `[ui]` du fichier `app.ini`, ajouter `obsidian` à la liste `THEMES` existante, puis définir `DEFAULT_THEME = obsidian` si souhaité. Exemple pour une liste standard :

```ini
[ui]
THEMES = forgejo-auto,forgejo-light,forgejo-dark,obsidian
DEFAULT_THEME = obsidian
```

3. Redémarrer Forgejo, puis choisir `obsidian` dans les paramètres d’apparence du compte. Un compte avec une préférence enregistrée peut ignorer le thème par défaut.

La page d’accueil native reçoit aussi le fond noir, des titres plus sobres et des blocs assortis. Pour appliquer le thème aux visiteurs non connectés et aux nouveaux comptes, définir `DEFAULT_THEME = obsidian` dans `[ui]`. Les comptes existants conservent leur préférence personnelle. Les styles d’accueil ciblent la structure native `.home` ; une page d’accueil personnalisée peut demander une adaptation.

Le CSS importe le thème natif à l’URL relative `./theme-forgejo-dark.css` ; les deux sont servis depuis `/assets/css/`. Ne pas renommer le fichier natif ni le remplacer.

## Personnalisation

Les composants conservent les arrondis natifs de Forgejo. Les ombres des cartes et fenêtres modales sont supprimées pour un rendu plus sobre. Les avatars et indicateurs de statut gardent leur forme native.

Les couleurs se règlent au début du CSS. `--color-primary` est l’accent principal ; les variables `--color-primary-*` définissent ses nuances. `--color-body`, `--color-box-body` et `--color-nav-bg` définissent les surfaces.

## Vérification et compatibilité

Variables comparées au thème officiel de la branche `forgejo` le 31 octobre 2026. Aucune instance Forgejo n’était disponible pour valider le rendu réel. Vérifier sur votre version les dépôts, issues, formulaires, menus, diffs et éditeurs avant activation générale ; les personnalisations CSS peuvent évoluer entre versions.

Pour revenir au thème natif, choisir `forgejo-dark` et restaurer la valeur précédente de `DEFAULT_THEME` si modifiée.

Documentation : https://forgejo.org/docs/latest/contributor/customization/
Source du thème natif : https://codeberg.org/forgejo/forgejo/src/branch/forgejo/web_src/css/themes/theme-forgejo-dark.css



