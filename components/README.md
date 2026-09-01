# Composants

Ce dossier accueillera les composants de l'ISI **au fur et à mesure qu'ils seront validés en atelier** : boutons, cartes, en-têtes, navigation, formulaires, pieds de page.

Il est volontairement vide en version 0.1 : les composants ne peuvent être figés tant que les fondations ([`../tokens/`](../tokens/)) n'ont pas été validées par la direction / la communication.

## Ce qui est déjà relevé sur le site officiel

Le bouton principal de [groupeisi.com](https://www.groupeisi.com/) présente les caractéristiques suivantes, à confirmer en atelier avant d'en faire un composant :

| Propriété | Valeur relevée |
|---|---|
| Fond | `#041F4E` (couleur primaire) |
| Texte | `#FFFFFF`, Amiko 700 |
| Rayon de bordure | `6px` |

## Comment un composant sera documenté

Un composant par fichier (`bouton.md`, `carte.md`, `en-tete.md`…), contenant :

1. **À quoi il sert** et dans quels cas ne pas l'employer.
2. **Ses variantes** (par exemple : bouton principal, secondaire, désactivé) — nommées par rôle, jamais par apparence.
3. **Les tokens qu'il consomme**, référencés par leur nom (`marque.primaire`, `space-md`) et jamais par une valeur écrite en dur.
4. **Ses états** : repos, survol, focus clavier, actif, désactivé.
5. **Ses règles d'accessibilité** : contraste, cible tactile minimale de 44 × 44 px, focus visible.
6. **La date et le cadre de sa validation.**

## Ordre de travail proposé

- [ ] Bouton (principal, secondaire, désactivé)
- [ ] Carte (formation, actualité)
- [ ] En-tête et navigation principale
- [ ] Pied de page
- [ ] Champs de formulaire (candidature, contact)
