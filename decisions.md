# Décisions

Registre des arbitrages du Design System ISI. Chaque décision indique **ce qui a été tranché**, **pourquoi**, et **comment revenir dessus**. Toute décision peut être annulée par la direction ou la communication de l'ISI.

Décisions D1 à D11 prises le **2 septembre 2026**, sur délégation explicite du responsable du projet, faute de retour de la direction à cette date. Elles visent à débloquer la production, pas à se substituer à une validation institutionnelle.

---

## D1 — Accent : `#0C71C3`, et rejet de trois candidats

**Tranché.** L'accent reste `#0C71C3`. Sont écartés :

| Candidat | Motif du rejet |
|---|---|
| `#2EA3F2` | Valeur par défaut du thème Divi, jamais choisie par l'ISI. Contraste **2,75:1** sur blanc — inutilisable pour du texte ou un élément d'interface. |
| `#1863DC` | Couleur par défaut du plugin de bandeau cookies. Retenue comme « Bleu Action » dans le jeu de tokens antérieur : la provenance ne tient pas. |
| `#F0B429` | Aucune trace sur le site officiel. Contraste **1,86:1** sur blanc. |

**Pourquoi** : une couleur affichée n'est pas une couleur choisie. Trois des quatre couleurs de marque du jeu antérieur provenaient en réalité d'un thème WordPress ou d'un plugin. Les faire entrer dans la charte reviendrait à graver dans le marbre les réglages par défaut d'un outil.

**Réversible** : si la communication confirme que le bleu vif de la charte est bien `#1863DC`, remplacer `marque.accent` dans `tokens/colors.json` — aucun autre fichier n'en dépend.

---

## D2 — Couleurs d'état : tranchées, plus en `"a-verifier"`

**Tranché.** Les quatre états passent en triplets texte / fond / bordure exploitables.

**Pourquoi** : une couleur d'erreur ne porte pas d'identité. Aucune institution n'a de rouge d'erreur propre, et laisser ces quatre valeurs en attente bloquait tout formulaire et tout message d'interface pour un gain de rigueur nul. Elles sont marquées `confiance: "moyenne — fonctionnel, non identitaire"` et restent distinctes des couleurs de marque.

**Correction au passage** : le rouge `#DC2626` du jeu antérieur ne donne que **4,41:1** sur son propre fond et échoue WCAG AA. Remplacé par `#B3261E` (**5,98:1**). Les trois autres états ont été vérifiés et passent.

**Réversible** : ces valeurs sont regroupées sous `etats` dans `tokens/colors.json`.

---

## D3 — Logo détouré : dépannage interne, jamais diffusé

**Tranché.** Le logo détouré automatiquement et sa silhouette blanche sont des **dérivés non officiels**. Ils peuvent servir aux maquettes de travail et aux ateliers. Ils ne doivent apparaître sur **aucun support diffusé** — site, plaquette, présentation externe, réseaux sociaux.

**Pourquoi** : un détourage automatique sur un JPEG laisse une frange de pixels compressés sur les contours, et une silhouette redessinée est une recréation du logo — précisément ce que `guidelines.md` interdit. Le fichier officiel reste `assets/logos/isi-logo-original.jpg`.

**Levée du blocage** : obtenir les fichiers vectoriels (SVG / EPS / AI) et la version monochrome auprès de la communication. C'est la demande n°1.

---

## D4 — Amiko servie par Google Fonts : validé

**Tranché.** Aucun binaire à fournir. Amiko est sous licence SIL Open Font License, ce qui autorise l'usage web, l'auto-hébergement et la redistribution.

**Pourquoi** : c'est exactement ce que fait déjà le site officiel, qui la tire de Google Fonts puis l'auto-héberge en `@font-face`. L'absence de `@font-face` local dans un outil de compilation n'est pas un défaut de charte.

**Recommandé** : auto-héberger les trois graisses (400 / 600 / 700) pour la performance et pour ne pas dépendre d'un tiers.

---

## D5 — JetBrains Mono adoptée comme police monospace

**Tranché.** Substitution acceptée et inscrite comme telle.

**Pourquoi** : la charte ISI n'a pas de monospace (`typography.json` porte `monospace: "a-verifier"`). Pour une école d'informatique, du code lisible dans les supports est un besoin réel. JetBrains Mono est sous licence Apache 2.0, dessinée pour la lecture de code, et se marie sans heurt avec Amiko.

---

## D6 — Lucide adopté comme jeu d'icônes

**Tranché.** Substitution acceptée et inscrite comme telle.

**Pourquoi** : aucun jeu d'icônes ISI n'existe. Lucide est sous licence MIT, cohérent en graisse de trait, et sa neutralité évite d'installer un style graphique qui deviendrait de fait la charte iconographique de l'ISI sans que personne ne l'ait décidé.

**À signaler en atelier** : si l'ISI veut un jeu propre, c'est un chantier distinct, à ne pas lancer avant validation des fondations.

---

## D7 — Photographies : aucune image générée ou empruntée

**Tranché.** Tous les visuels restent des réservations « photo à fournir ». Aucune banque d'images, aucune image générée, aucun visuel emprunté à un autre établissement.

**Pourquoi** : une photo de campus qui n'est pas celle de l'ISI décrédibilise l'ensemble dès la première relecture par quelqu'un qui connaît les lieux, et pose un problème de droits.

**Levée du blocage** : constituer une photothèque — campus, salles, étudiants — avec les autorisations de droit à l'image.

---

## D8 — Rayons et élévations : adoptés, avec correction du bouton

**Tranché.** Les échelles de rayon et d'élévation du jeu de tokens antérieur sont reprises (`tokens/radius.json`, `tokens/elevation.json`), à une correction près : **`radius-md` passe de 10px à 6px**, valeur réellement relevée sur les boutons du site officiel.

**Pourquoi** : ces échelles sont cohérentes et les ombres teintées en bleu ISI corroborent le `box-shadow: #041F4E` relevé sur les images du site. Autant les garder plutôt que les réinventer. Mais quand le site officiel donne une valeur, elle prime sur une proposition.

---

## D9 — Échelle typographique : celle de ce dépôt fait foi

**Tranché.** L'échelle à 5 niveaux (`titre-1`, `titre-2`, `titre-3`, `texte-courant`, `legende`), en `rem`, base 16 px, avec paliers responsive, reste la référence.

**Pourquoi** : le jeu antérieur propose 7 rôles en pixels fixes (48 / 30 / 20 / 16 / 15 / 13 / 12) sans paliers responsive et avec un texte courant à 15 px. Les tailles en pixels fixes ignorent le réglage de taille de police du navigateur, ce qui pénalise les lecteurs malvoyants.

**Réservé** : les rôles `label` et `kicker` du jeu antérieur sont utiles et pourront être ajoutés en v0.3 s'ils s'avèrent nécessaires aux composants.

---

## D10 — Données chiffrées fictives : filigrane obligatoire

**Tranché.** Tout écran, slide ou maquette contenant des chiffres inventés porte une mention **« données fictives »** visible sur l'écran lui-même — pas seulement dans une note de bas de page ou un README.

**Pourquoi** : un effectif ou un taux d'insertion inventé dans une maquette d'école finit systématiquement par être recopié dans un vrai document. Le coût du filigrane est nul, celui d'un chiffre faux en communication institutionnelle ne l'est pas.

---

## D11 — Ce dépôt est la source unique

**Tranché.** `design-system-isi` fait foi. Le fichier `Desktop/Seminaire ISI IA/Design System/isi-design-tokens.md` devient un document historique : ce qu'il avait de bon a été repris ici, ses erreurs de provenance et son défaut de contraste corrigés.

**Pourquoi** : deux jeux de tokens qui divergent sur les couleurs de marque, c'est la garantie que les deux seront faux dans six mois.

---

## En attente de la direction / de la communication

Ces points ne peuvent pas être tranchés en interne :

- [ ] **Fichiers sources du logo** — SVG / EPS / AI, version monochrome, version sur fond sombre *(bloquant pour toute production imprimée ou sur fond coloré)*
- [ ] **Validation des trois bleus** — `#041F4E` (confiance haute), `#1D4E79` et `#0C71C3` (confiance moyenne)
- [ ] **Photothèque** avec autorisations de droit à l'image
- [ ] **Visibilité du dépôt** — recommandation : le passer en privé jusqu'à validation *(voir README)*
- [ ] **Accès à un outil interne réel** (ERP, espace étudiant) si le tableau de bord doit devenir une recréation plutôt qu'une proposition
