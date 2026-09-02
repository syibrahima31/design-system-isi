# ISI — Design System

**Version 0.2 — dérivée du site officiel, à valider par la direction / la communication.**

Ce dépôt rassemble les fondations visuelles de l'ISI (Institut Supérieur d'Informatique, Groupe ISI) sous forme de *tokens* réutilisables : couleurs, typographie, espacement, rayons, élévation. Il ne s'agit pas encore d'une charte validée, mais d'un relevé documenté de l'existant, structuré pour pouvoir être discuté puis approuvé.

## Statut

| | |
|---|---|
| Version | 0.2.0 |
| Statut | Brouillon de travail — **les couleurs d'identité n'ont pas été validées par l'ISI à ce jour** |
| Date du relevé | 1er septembre 2026 |
| Arbitrages | 2 septembre 2026 — voir [`decisions.md`](decisions.md) |
| Source | [https://www.groupeisi.com/](https://www.groupeisi.com/) |

Chaque token porte un niveau de confiance (`haute` / `moyenne`) et l'indication de sa source. **Rien n'a été inventé pour combler un trou** : ce qui n'a pas pu être établi porte la valeur `"a-verifier"`, et ce qui a été tranché faute de retour institutionnel est motivé dans [`decisions.md`](decisions.md).

## Structure du dépôt

```
design-system-isi/
  README.md            ce fichier
  guidelines.md        règles d'usage (logo, couleurs, typographie, espacement)
  decisions.md         registre des arbitrages, avec motif et réversibilité
  tokens/
    colors.json        couleurs de marque, neutres, états
    typography.json    police et échelle typographique
    spacing.json       échelle d'espacement
    radius.json        rayons de bordure
    elevation.json     ombres
  components/
    README.md          composants à venir
  assets/
    logos/             logo et favicon officiels récupérés sur le site
    images/            visuels de la charte (vide pour l'instant)
```

## Source des couleurs

Les couleurs proviennent de deux relevés croisés effectués sur [groupeisi.com](https://www.groupeisi.com/) :

1. **Analyse du code source et des feuilles de style** de la page d'accueil et de la page « Présentation ».
2. **Analyse des pixels du logo officiel**, pour vérifier que les couleurs du CSS correspondent bien à celles de la marque.

La couleur primaire **`#041F4E`** (bleu marine) est confirmée par les deux relevés : c'est la couleur dominante non-blanche du logo (13 % des pixels) *et* celle du fond des boutons, des titres, du dégradé de la section d'accueil et des ombres dans le CSS.

Les couleurs secondaire (`#1D4E79`) et accent (`#0C71C3`) sont relevées avec une confiance **moyenne** et doivent être confirmées — le détail de la preuve et du doute est inscrit dans [`tokens/colors.json`](tokens/colors.json).

Plusieurs couleurs visibles sur le site ont été **volontairement écartées** parce qu'elles proviennent du thème WordPress (Divi), d'un plugin de bandeau cookies ou d'un logo tiers, et non d'un choix de l'ISI. Elles sont listées dans `marque.ecartees` du même fichier, avec leur motif de rejet.

Les couleurs d'état (succès, erreur, avertissement, information) n'existent pas sur le site. Elles ont été **tranchées le 2 septembre 2026** parce qu'elles sont fonctionnelles et ne portent pas d'identité — voir la décision D2. Tous les rapports de contraste inscrits dans les tokens ont été calculés, pas estimés.

## Source du logo

Le logo est celui affiché dans l'en-tête du site officiel :

| Fichier | Source |
|---|---|
| `assets/logos/isi-logo-original.jpg` | `https://www.groupeisi.com/wp-content/uploads/2018/11/LOGO-NEW-GROUP.jpg` |
| `assets/logos/isi-favicon-192.png` | `https://www.groupeisi.com/wp-content/uploads/2020/08/cropped-G1-192x192.png` |

⚠️ **Limite connue** : le logo disponible publiquement est un **JPEG de 2825 × 1681 px (398 Ko) à fond blanc opaque**, sans transparence ni version vectorielle. Il est inutilisable sur fond coloré et se dégrade à l'agrandissement. **Il faut demander à la direction de la communication les fichiers sources (SVG, EPS ou AI) ainsi qu'une version monochrome** avant toute production. Le fichier présent ici est un dépannage, pas une référence.

Tout logo détouré ou redessiné à partir de ce JPEG est un **dérivé non officiel**, réservé aux maquettes de travail et interdit sur les supports diffusés (décision D3).

## Police et substitutions

La police du site est **Amiko** (Google Fonts, licence SIL Open Font License), auto-hébergée, en graisses 400 / 600 / 700. Elle est reprise telle quelle. Voir [`tokens/typography.json`](tokens/typography.json).

Deux éléments n'existent pas dans la charte ISI et ont été **substitués faute de source**. Ce sont des choix par défaut assumés, pas des éléments d'identité :

| Besoin | Substitution retenue | Licence | Décision |
|---|---|---|---|
| Police monospace | JetBrains Mono | Apache 2.0 | D5 |
| Jeu d'icônes | Lucide | MIT | D6 |

Aucune photographie n'est fournie : tous les emplacements de visuels restent des réservations « photo à fournir » (décision D7).

## Origine de la structuration

L'organisation de ce dépôt — nombre de niveaux typographiques, ratio de l'échelle, grille d'espacement de 4 px, découpage des tokens — s'inspire de pratiques de structuration observées sur des sites d'écoles et d'instituts comparables (notamment le design system public de l'EPFL, ainsi que les sites de 42 et de l'École Supérieure Polytechnique de Dakar).

**Seule la méthode de structuration a été reprise.** Aucune couleur, aucune police, aucun logo ni aucun élément d'identité visuelle appartenant à ces établissements n'a été repris : ces éléments sont leur propriété. Toutes les valeurs d'identité de ce dépôt proviennent exclusivement du site de l'ISI.

## Visibilité du dépôt

Le dépôt est actuellement **public**. Recommandation : le passer en **privé** jusqu'à validation, parce qu'il diffuse le logo de l'ISI dans une forme dont les droits ne sont pas établis, et des couleurs marquées `confiance: moyenne` qu'un tiers peut prendre pour la charte officielle.

`Settings → General → Danger Zone → Change visibility`, ou :

```bash
gh repo edit syibrahima31/design-system-isi --visibility private --accept-visibility-change-consequences
```

## Prochaines étapes

Les arbitrages déjà pris sont dans [`decisions.md`](decisions.md). Ce qui reste en attente de la direction ou de la communication :

- [ ] Fichiers sources vectoriels du logo (+ version monochrome et version sur fond sombre)
- [ ] Validation des trois bleus de marque
- [ ] Photothèque (campus, salles, étudiants) avec autorisations de droit à l'image
- [ ] Passage du dépôt en privé
- [ ] Accès à un outil interne réel (ERP, espace étudiant) si le tableau de bord doit devenir une recréation
- [ ] Documentation des premiers composants dans `components/` au fur et à mesure des ateliers
