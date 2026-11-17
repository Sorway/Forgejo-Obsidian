<div align="center">

# Obsidian

Thème sombre pour Forgejo, avec des fonds anthracite, des liens pêche pastel et des touches d’abricot sur les interactions et le calendrier de contributions.

![Forgejo](https://img.shields.io/badge/Forgejo-202022?style=flat-square&logo=forgejo&logoColor=D8B196)
![Testé jusqu’à 17.0.1](https://img.shields.io/badge/test%C3%A9_jusqu%E2%80%99%C3%A0-17.0.1-D8B196?style=flat-square&labelColor=202022)

[Installation](#installation) · [Palette](#palette) · [Personnalisation](#personnalisation)

</div>

Le thème étend `forgejo-dark` : la coloration du code, les diffs et les couleurs de statut restent ceux de Forgejo. L’installation se limite à un fichier CSS.

## Palette

| Usage | Couleur | Valeur CSS |
| :--- | :--- | :--- |
| Fond principal | `#111112` | `--color-body` |
| Panneaux | `#181819` | `--color-box-body` |
| Menus | `#202022` | `--color-menu` |
| Bordures | `#363639` | `--color-secondary` |
| Texte principal | `#DEDEE0` | `--color-text` |
| Accent abricot pastel | `#D8B196` | `--color-primary` |
| Liens pêche pastel | `#D2AB96` | `--color-text-link` |

## Installation

L’installation nécessite un accès aux fichiers de l’instance et à sa configuration `app.ini`.

### 1. Copier le thème

Placer [theme-obsidian.css](theme-obsidian.css) dans le dossier personnalisé de Forgejo :

```text
$FORGEJO_CUSTOM/
└── public/
    └── assets/
        └── css/
            └── theme-obsidian.css
```

Le chemin du dossier personnalisé est indiqué dans **Administration du site → Configuration**. Avec Docker, utiliser le dossier personnalisé persistant monté dans le conteneur.

> Le fichier importe `./theme-forgejo-dark.css`, fourni par Forgejo. Conserver ce nom et laisser le thème natif disponible dans les assets servis par l’instance.

### 2. Déclarer le thème

Dans la section `[ui]` de `app.ini`, ajouter `obsidian` à la liste `THEMES` existante. Pour une configuration standard :

```ini
[ui]
THEMES = forgejo-auto,forgejo-light,forgejo-dark,obsidian
DEFAULT_THEME = obsidian
```

Conserver les autres thèmes déjà déclarés. `DEFAULT_THEME` est facultatif : il définit l’apparence des visiteurs et des comptes sans préférence personnelle.

### 3. Activer Obsidian

Redémarrer Forgejo, puis sélectionner **obsidian** dans les paramètres d’apparence du compte. Recharger la page avec **Ctrl + F5** pour actualiser le CSS en cache.

Les comptes ayant déjà choisi un thème conservent leur préférence, même si `DEFAULT_THEME` change.

## Personnalisation

Les couleurs sont regroupées dans le bloc `:root` au début du CSS. Modifier les variables concernées pour adapter la palette :

```css
:root {
  --color-body: #111112;
  --color-box-body: #181819;
  --color-nav-bg: #0c0c0d;
  --color-primary: #d8b196;
  --color-text-link: #d2ab96;
}
```

Pour changer l’accent, ajuster aussi les variables `--color-primary-*`, `--color-text-link`, `--color-text-link-visited`, `--color-accent`, `--color-small-accent`, `--color-highlight-*`, `--color-selection-*` et `--color-reaction-*-bg` afin de garder des liens, survols, sélections et états actifs cohérents.

Le thème couvre aussi la page d’accueil native. Une page personnalisée peut demander des ajustements.

## Compatibilité

**Testé jusqu’à Forgejo 17.0.1**.

Les versions suivantes restent à tester.

### Revenir au thème natif

Sélectionner **forgejo-dark** dans les paramètres d’apparence et, si nécessaire, restaurer la valeur précédente de `DEFAULT_THEME`.
