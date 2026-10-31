<div align="center">

# Obsidian

### Un thème sombre et sobre pour Forgejo.

Des noirs nuancés, un accent mauve discret et une interface qui laisse la place au code.

![Forgejo](https://img.shields.io/badge/Forgejo-th%C3%A8me_personnalis%C3%A9-FB923C?style=for-the-badge&logo=forgejo&logoColor=white&labelColor=202025)
![CSS](https://img.shields.io/badge/CSS-un_seul_fichier-A29BB8?style=for-the-badge&labelColor=202025)
![Apparence](https://img.shields.io/badge/Apparence-sombre-CECED7?style=for-the-badge&labelColor=202025)
![Testé jusqu’à Forgejo 17.0.1](https://img.shields.io/badge/Test%C3%A9_jusqu%E2%80%99%C3%A0-Forgejo_17.0.1-86C995?style=for-the-badge&labelColor=202025)

[Installation](#installation) · [Palette](#palette) · [Personnalisation](#personnalisation)

</div>

---

## Une interface plus douce

Obsidian habille Forgejo de surfaces anthracite, de bordures discrètes et de textes hiérarchisés. Le thème s’appuie sur `forgejo-dark` pour hériter de la coloration syntaxique, des diffs et des couleurs de statut.

- **Noirs neutres** : plusieurs niveaux de profondeur pour distinguer le fond, les panneaux et les menus.
- **Accent mauve grisé** : liens, sélections et interactions assortis.
- **Lecture confortable** : textes secondaires adoucis et focus clavier visibles.
- **Intégration légère** : un fichier CSS, sans JavaScript, police distante ni modification des templates.
- **Détails natifs préservés** : arrondis, avatars et indicateurs conservent leurs formes Forgejo.

## Palette

| Usage | Couleur | Valeur CSS |
| :--- | :--- | :--- |
| Fond principal | `#111114` | `--color-body` |
| Panneaux | `#18181C` | `--color-box-body` |
| Menus | `#202025` | `--color-menu` |
| Bordures | `#33333C` | `--color-secondary` |
| Texte principal | `#DDDDE4` | `--color-text` |
| Accent mauve | `#A29BB8` | `--color-primary` |

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
  --color-body: #111114;
  --color-box-body: #18181c;
  --color-nav-bg: #0c0c0f;
  --color-primary: #a29bb8;
}
```

Pour changer l’accent, ajuster aussi les variables `--color-primary-*` afin de garder des survols, sélections et états actifs cohérents.

La page d’accueil native possède des styles dédiés : fond assorti, titres sobres et blocs harmonisés. Une page d’accueil personnalisée peut nécessiter des ajustements.

### Compatibilité

**Testé jusqu’à Forgejo 17.0.1**.

Le thème dépend des variables et de la structure HTML de Forgejo. La compatibilité avec les versions suivantes reste à vérifier. Après une mise à jour, vérifier les dépôts, issues, formulaires, menus, diffs et éditeurs.

### Revenir au thème natif

Sélectionner **forgejo-dark** dans les paramètres d’apparence et, si nécessaire, restaurer la valeur précédente de `DEFAULT_THEME`.