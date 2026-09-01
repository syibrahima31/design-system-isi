# ISI — Règles d'usage

**Version 0.1 — à valider par la direction / la communication.**

Ces règles encadrent l'emploi des éléments définis dans [`tokens/`](tokens/). Elles s'appliquent au site, aux supports numériques et aux documents produits par l'ISI.

---

## 1. Logo

Le logo est l'élément le plus sensible de la charte : c'est le seul qui identifie l'établissement de manière univoque.

**Interdits — sans exception :**

- ❌ **Ne jamais déformer** le logo. Tout redimensionnement se fait en conservant les proportions (ne jamais étirer en largeur ou en hauteur seule).
- ❌ **Ne jamais recolorer** le logo, ni en changer une partie. La seule variante admise est une version monochrome **fournie par la communication**, jamais recolorée soi-même.
- ❌ **Ne jamais faire pivoter** le logo, ni l'incliner, ni le mettre en perspective.
- ❌ **Ne pas ajouter** d'ombre portée, de contour, de biseau, de reflet ou de dégradé.
- ❌ **Ne pas recadrer** le logo ni en isoler un fragment pour en faire un pictogramme.
- ❌ **Ne pas placer le logo sur un fond chargé** (photo texturée, motif) ni sur un fond dont le contraste est insuffisant.

**À respecter :**

- ✅ **Zone de protection** : réserver autour du logo une marge vide au moins égale à la hauteur de la lettre « I » du sigle. Aucun texte ni élément graphique ne doit entrer dans cette zone.
- ✅ **Taille minimale** : 90 px de large en écran, 25 mm en impression. En dessous, le sigle devient illisible.
- ✅ **Fond** : utiliser le logo sur `neutres.fond-clair` (`#FFFFFF`). Sur fond sombre, employer la version dédiée fournie par la communication — pas le fichier actuel, dont le fond blanc est opaque.

> ⚠️ **Limite actuelle** : le seul fichier disponible est un JPEG à fond blanc opaque, sans version vectorielle (voir le [README](README.md)). Tant que les fichiers sources n'ont pas été obtenus, éviter tout agrandissement et toute pose sur fond coloré.

---

## 2. Couleurs

### Couleur primaire — `#041F4E`

La couleur primaire est **réservée aux titres et aux boutons d'action**. C'est ce qui lui donne sa valeur de signal : plus elle est employée, moins elle signifie quelque chose.

- ✅ Titres de niveau 1 et 2, boutons d'action principaux, fonds de section sombres, éléments de navigation actifs.
- ❌ Ne pas l'employer pour du texte courant, des aplats décoratifs étendus, ni des bordures fines.

### Règles générales

- **Une seule action principale par écran ou par section.** Un seul bouton peut porter la couleur primaire ; les actions secondaires utilisent un bouton bordé ou un lien.
- **Les couleurs d'état ne servent qu'à leur état.** Ne jamais employer le rouge d'erreur comme couleur d'accent décoratif, ni le vert de succès pour un simple aplat.
- **Contraste** : viser un rapport d'au moins **4,5:1** pour le texte courant et **3:1** pour les gros titres et les éléments d'interface (WCAG AA). Les rapports vérifiés sont inscrits dans [`tokens/colors.json`](tokens/colors.json).
- **La couleur ne doit jamais être le seul porteur d'information.** Un champ en erreur porte aussi un message et une icône, pas seulement une bordure rouge.
- **Ne pas introduire de couleur hors palette.** Si un besoin n'est pas couvert, le signaler en atelier plutôt que d'inventer une teinte.
- **Les couleurs marquées `"a-verifier"` ne doivent pas partir en production** tant qu'elles n'ont pas été tranchées.

---

## 3. Typographie

- **Une seule police : Amiko**, en 400 / 600 / 700. Ce sont les seules graisses chargées ; **ne jamais simuler** un gras ou un italique absent (pas de faux gras).
- **Respecter les cinq niveaux** de [`tokens/typography.json`](tokens/typography.json) : `titre-1`, `titre-2`, `titre-3`, `texte-courant`, `legende`. Ne pas créer de taille intermédiaire.
- **Un seul `titre-1` par page.** La hiérarchie se descend sans sauter de niveau.
- **Taille plancher : 14 px.** Aucun texte destiné à être lu ne descend en dessous.
- **Longueur de ligne** : viser 60 à 80 caractères pour les paragraphes.
- **Ne pas justifier** le texte ; l'alignement à gauche reste la règle.
- **Pas de titres tout en capitales** sur plus de quelques mots : la lecture s'en trouve ralentie.

---

## 4. Espacement

- **Toutes les marges et tous les remplissages proviennent de [`tokens/spacing.json`](tokens/spacing.json)** — grille de 4 px. Aucune valeur intermédiaire (10, 15, 25 px…) ne doit être introduite.
- **La proximité traduit la relation** : deux éléments liés sont plus proches l'un de l'autre que du groupe voisin. L'écart intérieur d'un groupe est toujours inférieur à l'écart qui le sépare du groupe suivant.
- **Valeur par défaut : `space-md` (16 px)** pour le remplissage des cartes et l'écart entre paragraphes.
- **`space-xxl` (48 px)** sépare deux sections de page.

---

## 5. Portée de ce document

Ce document décrit un état **relevé**, pas encore **approuvé**. Toute règle peut être corrigée par la direction ou la communication de l'ISI ; les corrections seront versionnées dans ce dépôt.
