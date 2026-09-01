# ISI — Design System

**Version 0.1 — dérivée du site officiel, à valider par la direction / la communication.**

Ce dépôt rassemble les fondations visuelles de l'ISI (Institut Supérieur d'Informatique, Groupe ISI) sous forme de *tokens* réutilisables : couleurs, typographie, espacement. Il ne s'agit pas encore d'une charte validée, mais d'un relevé documenté de l'existant, structuré pour pouvoir être discuté puis approuvé.

## Statut

| | |
|---|---|
| Version | 0.1.0 |
| Statut | Brouillon de travail — **aucune valeur n'a été validée par l'ISI à ce jour** |
| Date du relevé | 1er septembre 2026 |
| Source | [https://www.groupeisi.com/](https://www.groupeisi.com/) |

Chaque token porte un niveau de confiance (`haute` / `moyenne`) et l'indication de sa source. Les valeurs qui n'ont pas pu être établies avec certitude portent la valeur `"a-verifier"` : **rien n'a été inventé pour combler un trou.**

## Structure du dépôt

```
design-system-isi/
  README.md            ce fichier
  guidelines.md        règles d'usage (logo, couleurs, typographie, espacement)
  tokens/
    colors.json        couleurs de marque, neutres, états
    typography.json    police et échelle typographique
    spacing.json       échelle d'espacement
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

Plusieurs couleurs visibles sur le site ont été **volontairement écartées** parce qu'elles proviennent du thème WordPress (Divi), d'un plugin de bandeau cookies ou d'un logo tiers, et non d'un choix de l'ISI. Elles sont listées dans `marque.ecartees` du même fichier.

Aucune couleur d'état (succès, erreur, avertissement, information) n'existe sur le site : elles sont donc en `"a-verifier"`, accompagnées d'une proposition accessible clairement identifiée comme telle.

## Source du logo

Le logo est celui affiché dans l'en-tête du site officiel :

| Fichier | Source |
|---|---|
| `assets/logos/isi-logo-original.jpg` | `https://www.groupeisi.com/wp-content/uploads/2018/11/LOGO-NEW-GROUP.jpg` |
| `assets/logos/isi-favicon-192.png` | `https://www.groupeisi.com/wp-content/uploads/2020/08/cropped-G1-192x192.png` |

⚠️ **Limite connue** : le logo disponible publiquement est un **JPEG de 2825 × 1681 px (398 Ko) à fond blanc opaque**, sans transparence ni version vectorielle. Il est inutilisable sur fond coloré et se dégrade à l'agrandissement. **Il faut demander à la direction de la communication les fichiers sources (SVG, EPS ou AI) ainsi qu'une version monochrome** avant toute production. Le fichier présent ici est un dépannage, pas une référence.

## Police

La police du site est **Amiko** (Google Fonts), auto-hébergée, en graisses 400 / 600 / 700. Elle est reprise telle quelle dans le Design System. Voir [`tokens/typography.json`](tokens/typography.json).

## Origine de la structuration

L'organisation de ce dépôt — nombre de niveaux typographiques, ratio de l'échelle, grille d'espacement de 4 px, découpage des tokens — s'inspire de pratiques de structuration observées sur des sites d'écoles et d'instituts comparables (notamment le design system public de l'EPFL, ainsi que les sites de 42 et de l'École Supérieure Polytechnique de Dakar).

**Seule la méthode de structuration a été reprise.** Aucune couleur, aucune police, aucun logo ni aucun élément d'identité visuelle appartenant à ces établissements n'a été repris : ces éléments sont leur propriété. Toutes les valeurs d'identité de ce dépôt proviennent exclusivement du site de l'ISI.

## Prochaines étapes

- [ ] Faire valider la couleur primaire, la secondaire et l'accent par la direction / la communication
- [ ] Obtenir les fichiers sources vectoriels du logo (+ version monochrome et version sur fond sombre)
- [ ] Trancher les couleurs d'état actuellement en `"a-verifier"`
- [ ] Documenter les premiers composants dans `components/` au fur et à mesure des ateliers
