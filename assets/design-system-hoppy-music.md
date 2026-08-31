# Design System — Hoppy Music

> Site vitrine pour **Hoppy Music**, collectif organisant des **sessions** et **festivals** mêlant musique éclectique, artistes locaux et bières artisanales à **Louvres, Val d'Oise (95)**.
> Stack cible : **Next.js + Payload CMS**

---

## 1. Identité de marque

### 1.1 Positionnement

Hoppy Music organise deux formats d'événements :

- **Hoppy Music Festival (HMF)** — événement annuel, plusieurs scènes, têtes d'affiche, foodtrucks & bières artisanales. 1ère édition : 14 septembre 2024, Louvres.
- **Hoppy Music Session (HMS)** — soirées plus intimistes, scène locale, ambiance décontractée, thématiques variées (ex : Édition Roller). Prix accessible (5€, gratuit -18 ans).

**Baseline :** Musiques éclectiques. Artistes locaux. Bières artisanales.

### 1.2 Ton & personnalité

| Attribut         | Description                                                         |
| ---------------- | ------------------------------------------------------------------- |
| **Sombre**       | Fond noir dominant, ambiance nocturne / concert                     |
| **Immersif**     | Plein écran, grandes images, peu de distractions visuelles          |
| **Éclectique**   | Mélange de genres musicaux, visuels colorés sur fond monochrome     |
| **Clean**        | Minimaliste dans la mise en page, espaces généreux, peu d'éléments  |
| **Festif**       | Énergie des photos live, illustrations doodle, houblon multicolore  |

### 1.3 Logos & symboles

| Élément                    | Fichier                      | Usage                                                          |
| -------------------------- | ---------------------------- | -------------------------------------------------------------- |
| **Logo texte complet**     | `HOPPY_MUSIC_Logo.png`       | Hero, footer — version blanche sur fond sombre                 |
| **Symbole houblon noir**   | Silhouette dans le "O"       | Favicon, centre du header nav, loader                          |
| **Symbole houblon coloré** | `symbole_hoppy_music.png`    | Élément décoratif, illustrations, pages événement              |

**Règles logo :**

- Zone de protection : espace min. autour du logo = hauteur du "O"
- Taille minimale : 120px de large (desktop), 80px (mobile)
- Toujours blanc sur fond sombre — jamais sur fond clair sans overlay
- Le houblon dans le "O" ne doit jamais être séparé du logotype

---

## 2. Couleurs

### 2.1 Palette principale

| Nom          | Hex         | CSS Variable    | Usage                                  |
| ------------ | ----------- | --------------- | -------------------------------------- |
| **Noir**     | `#181617`   | `--color-bg`    | Fond principal du site                 |
| **Blanc**    | `#FBFCFB`   | `--color-text`  | Texte, icônes, bordures, éléments UI   |

### 2.2 Nuances fonctionnelles

| Nom              | Valeur                          | CSS Variable               | Usage                                 |
| ---------------- | ------------------------------- | -------------------------- | ------------------------------------- |
| Gris texte       | `#A0A0A0`                       | `--color-text-secondary`   | Texte secondaire, dates, métadonnées  |
| Gris surface     | `#2A2829`                       | `--color-surface`          | Cartes, surfaces surélevées           |
| Gris bordure     | `#3A3839`                       | `--color-border`           | Séparateurs, bordures subtiles        |
| Blanc 10%        | `rgba(251,252,251,0.10)`        | `--color-glass`            | Glassmorphism, overlays légers        |
| Blanc 60%        | `rgba(251,252,251,0.60)`        | `--color-overlay-light`    | Overlay texte sur image blur          |
| Noir 50%         | `rgba(24,22,23,0.50)`           | `--color-overlay-dark`     | Overlay sombre sur images (hero, HMF) |

### 2.3 Philosophie couleur

**Strictement noir & blanc pour l'UI.** Toute la couleur provient exclusivement :

- Des **photographies** de concerts (colorées, saturées, éclairages scéniques)
- Du **symbole houblon multicolore** (rose, cyan, jaune, rouge, vert)
- Du **fond blur** (`fond_hoppy_music.jpg`) utilisé en background de certaines sections

Ce contraste entre UI monochrome et richesse photographique/illustrative est le cœur de l'identité visuelle.

---

## 3. Typographie

### 3.1 Familles

| Police                | Poids          | CSS Variable       | Usage                                                  |
| --------------------- | -------------- | ------------------- | ------------------------------------------------------ |
| **Reem Kufi**         | Bold (700)     | `--font-heading`    | Titres, noms d'événements, navigation, noms d'artistes |
| **Quattrocento Sans** | Regular + Bold | `--font-body`       | Corps de texte, descriptions, UI, boutons              |
| **Permanent Marker**  | Regular (400)  | `--font-session`    | **Exclusivement** pour les éléments liés aux "Sessions" |

### 3.2 Échelle typographique

| Token              | Desktop | Mobile | Line-height | Police            | Usage                                    |
| ------------------ | ------- | ------ | ----------- | ----------------- | ---------------------------------------- |
| `--text-hero`      | 72px    | 40px   | 1.0         | Reem Kufi Bold    | Titre hero plein écran                   |
| `--text-h1`        | 48px    | 32px   | 1.1         | Reem Kufi Bold    | Titres de section                        |
| `--text-h2`        | 32px    | 24px   | 1.2         | Reem Kufi Bold    | Sous-titres, noms de headliners          |
| `--text-h3`        | 24px    | 20px   | 1.3         | Reem Kufi Bold    | Titres de cartes, artistes secondaires   |
| `--text-body`      | 16px    | 16px   | 1.6         | Quattrocento Sans | Corps de texte                           |
| `--text-small`     | 14px    | 14px   | 1.5         | Quattrocento Sans | Métadonnées, dates, légendes             |
| `--text-caption`   | 12px    | 12px   | 1.4         | Quattrocento Sans | Copyright, mentions légales              |
| `--text-session`   | 40px    | 28px   | 1.1         | Permanent Marker  | Mot "Session" dans les contextes HMS     |

### 3.3 Règles typographiques

- **Titres Reem Kufi** : toujours en MAJUSCULES avec `letter-spacing: 0.05em`
- **Permanent Marker** : réservée au mot "Session" et aux sous-titres d'éditions HMS (ex : "Édition Roller"). Jamais pour le Festival ni pour l'UI générale
- **Hiérarchie artistes** (ref. affiche HMF) : headliner en `--text-h2`, artistes secondaires en `--text-h3`, artistes tertiaires en `--text-body` bold — tous en Reem Kufi, séparés par des tirets `—`, letter-spacing large
- **Corps de texte** : pas d'italique ni de gras sauf liens et mots-clés importants

---

## 4. Imagerie & Illustrations

### 4.1 Photographies

| Type                       | Exemples fichiers                                                     | Caractéristiques                                              |
| -------------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Artistes sur scène**     | `HMSIMG12x`, `HMSIMG32x`, `HMSIMG42x`, `HMSIMG52x`, `HMSIMG62x`    | Éclairages scéniques saturés (violet, bleu, rose), cadrage serré, action |
| **Public / ambiance**      | `HMSIMG12x`                                                          | Contre-plongée, lumière dorée/crépuscule, face painting, barrières |
| **Acoustique / plein air** | `HMSIMG2`                                                            | Lumière naturelle, bleu ciel, scène intimiste, ambiance Session |

**Traitement des photos :**

- Jamais de filtre ou de désaturation — les couleurs vives des éclairages live sont l'identité
- Les photos en situation de concert (sombre + lumières colorées) fonctionnent naturellement sur fond `--color-bg`
- Les photos en plein air/lumière naturelle nécessitent un overlay sombre si du texte est superposé

### 4.2 Illustrations style Doodle

**Style :** inspiré Mr. Doodle / Keith Haring — trait blanc épais sur fond noir, motifs dessinés à la main, densité élevée, esprit joyeux et festif.

**Fichiers :** `illustration_1.png` (format paysage 16:9), `illustration_2.png` (format portrait 3:4)

**Motifs récurrents :**

- Musique : guitare, DJ aux platines, enceintes, vinyle, notes de musique, micro, bannière "LIVE", groupe sur scène
- Bière : chopes qui trinquent, houblon, canette
- Festival : chapiteau, guirlandes, foodtruck, feu de camp, soleil, tente camping
- Ambiance : cœurs, étoiles, personnages dansants, bras levés, mains rock

**Usages sur le site :**

| Usage                          | Description                                                              |
| ------------------------------ | ------------------------------------------------------------------------ |
| **Séparateurs de sections**    | Bande horizontale de doodles (extrait de `illustration_1.png`) entre deux sections |
| **Décoration de bords**        | Fragment d'illustration le long d'un bord de section, opacité réduite (10-20%) |
| **Icônes individuelles**       | Éléments extraits isolément (guitare, chope, vinyle...) comme icônes de rubrique |
| **Fond de section**            | Illustration complète en background très atténuée (`opacity: 0.05-0.10`) pour texturer une section fond noir |
| **Footer**                     | Fine bande doodle comme séparateur avant le copyright                    |

**Règles illustrations :**

- Toujours **blanc sur noir** (`--color-text` sur `--color-bg`), jamais inversé
- En décoration de fond, toujours très atténuées pour ne pas interférer avec le contenu
- Quand utilisées comme icônes individuelles, garder le trait épais et le style dessiné main — ne pas les vectoriser de manière lisse
- Les doodles ne remplacent jamais les icônes fonctionnelles UI (navigation, formulaires)

### 4.3 Affiches événements

| Type                  | Fichier de référence              | Caractéristiques                                          |
| --------------------- | --------------------------------- | --------------------------------------------------------- |
| **Affiche Festival**  | `affiche_hoppy_music_festival.jpg` | Fond blur + overlay sombre, houblon coloré grand format, typo Reem Kufi, hiérarchie artistes par taille, partenaires en bas, QR code |
| **Affiche Session**   | `affiche_hoppy_music_session.jpg`  | Fond blur sans overlay noir, "HOPPY MUSIC" en Reem Kufi Bold, "SESSION" en Permanent Marker, icônes décoratives (notes, mains rock) |
| **Affiche Standard**  | `affiche_standard.jpg`             | Fond blur + illustrations doodle blanches + houblon coloré central, logo petit en haut, baseline en bas — visuel générique hors événement |

### 4.4 Système de backgrounds

Le site alterne entre **trois types de fonds** pour rythmer le scroll :

| Fond                       | Rendu                                                    | Contenu autorisé par-dessus               |
| -------------------------- | -------------------------------------------------------- | ----------------------------------------- |
| **Fond noir uni**          | `background: var(--color-bg)`                            | Images + texte + illustrations            |
| **Fond blur**              | Image `fond_hoppy_music.jpg` ou flou CSS                 | **Texte uniquement** (pas d'images)       |
| **Fond noir + doodle**     | `--color-bg` avec illustration en filigrane (5-10%)      | Texte + images (le doodle reste subtil)   |

**Règles :**

- Les sections fond blur servent de **respiration visuelle** entre les sections denses
- Les photos de concert ne sont **jamais** floutées — le flou est réservé au fond abstrait multicolore
- Overlay sombre (`--color-overlay-dark`) obligatoire sur le hero et toute image servant de fond avec du texte par-dessus

### 4.5 Formats d'images

| Contexte           | Ratio        | Traitement                             |
| ------------------ | ------------ | -------------------------------------- |
| Hero               | Plein écran  | `object-fit: cover`, hauteur `100vh`   |
| Affiches événements | 3:4 portrait | Coins arrondis `--radius-md`          |
| Photos galerie     | 3:4 ou 16:9  | Selon l'original, pas de crop forcé    |
| Miniatures         | 1:1 carré    | `object-fit: cover`, `--radius-md`     |

---

## 5. Composants UI

### 5.1 Espacement

Base de 8px :

| Token        | Valeur | Usage                              |
| ------------ | ------ | ---------------------------------- |
| `--space-xs` | 4px    | Micro-espaces internes             |
| `--space-sm` | 8px    | Espaces entre éléments proches     |
| `--space-md` | 16px   | Padding interne de composants      |
| `--space-lg` | 24px   | Espaces entre groupes              |
| `--space-xl` | 48px   | Marges entre sections              |
| `--space-2xl`| 80px   | Grandes respirations               |
| `--space-3xl`| 120px  | Padding vertical des sections majeures |

### 5.2 Border-radius

| Token              | Valeur | Usage                        |
| ------------------ | ------ | ---------------------------- |
| `--radius-sm`      | 4px    | Tags, badges                 |
| `--radius-md`      | 8px    | Boutons, cartes, images      |
| `--radius-lg`      | 16px   | Modales, conteneurs larges   |
| `--radius-full`    | 9999px | Boutons pilule, avatars      |

### 5.3 Navigation

**Desktop — barre fixe (sticky header) :**

```
[ ÉVÉNEMENTS    NOTRE HISTOIRE ]    🍺(symbole houblon)    [ BOUTIQUE    CONTACT ]
```

- Fond : `rgba(24,22,23,0.85)` + `backdrop-filter: blur(12px)`
- Symbole houblon (silhouette) centré, cliquable → retour accueil
- Liens en Reem Kufi Bold, majuscules, `--text-small`, `letter-spacing: 0.1em`
- Hover : opacité 0.7, transition `--transition-fast`
- Au scroll : apparition du fond semi-transparent après le hero

**Mobile — menu burger :**

- Symbole houblon centré en haut, icône burger à droite
- Menu overlay plein écran, fond `--color-bg`
- Liens centrés verticalement, `--text-h2`, Reem Kufi Bold
- Animation : slide-in depuis la droite, `--transition-normal`
- Fermeture : croix en haut à droite

### 5.4 Boutons

**Bouton primaire (plein) :**

| Propriété       | Valeur                                          |
| --------------- | ----------------------------------------------- |
| Fond            | `--color-text` (#FBFCFB)                        |
| Texte           | `--color-bg` (#181617)                          |
| Police          | Quattrocento Sans Bold, 14px, majuscules        |
| Letter-spacing  | `0.05em`                                        |
| Padding         | `12px 32px`                                     |
| Border-radius   | `--radius-md` (8px)                             |
| Hover           | `opacity: 0.85`, `translateY(-1px)`             |
| Usage           | CTA principal : billetterie, inscription, achat |

**Bouton secondaire (outline) :**

| Propriété       | Valeur                                          |
| --------------- | ----------------------------------------------- |
| Fond            | `transparent`                                   |
| Bordure         | `1px solid var(--color-text)`                   |
| Texte           | `--color-text`                                  |
| Padding         | `12px 32px`                                     |
| Border-radius   | `--radius-md` (8px)                             |
| Hover           | fond `--color-glass`, bordure maintenue         |
| Usage           | Actions secondaires : en savoir plus, galerie   |

**Logique :** primaire pour l'engagement (acheter, réserver), secondaire pour l'exploration (voir plus, découvrir).

### 5.5 Cartes événements

Grille d'**affiches de festival** avec titre et numéro :

```
┌──────────────────────────┐
│                          │
│     [AFFICHE IMAGE]      │   ← Affiche 3:4, object-fit cover
│     (plein cadre)        │
│                          │
├──────────────────────────┤
│  HOPPY MUSIC FESTIVAL    │   ← Reem Kufi Bold, --text-h3
│  #1                      │   ← --text-small, --color-text-secondary
└──────────────────────────┘
```

- Fond carte : `--color-surface`
- Border-radius : `--radius-md`
- Padding bas : `--space-md`
- Hover : `translateY(-4px)` + `box-shadow: 0 8px 24px rgba(0,0,0,0.4)`
- Grille : 3 col. desktop / 2 col. tablette / 1 col. mobile, gap `--space-lg`

### 5.6 Section Hero (Accueil)

```
┌─────────────────────────────────────────────┐
│  [NAV : liens + symbole houblon centré]     │
├─────────────────────────────────────────────┤
│                                             │
│          (photo ou vidéo plein écran)        │
│          + overlay --color-overlay-dark      │
│                                             │
│              HOPPY                          │
│              MUSIC                          │   ← Logo complet centré
│                                             │
│         [ DÉCOUVRIR LE FESTIVAL ]           │   ← Bouton primaire
│                                             │
│              ↓ scroll indicator             │
└─────────────────────────────────────────────┘
```

- Background : `100vh`, `object-fit: cover`
- Logo centré vertical + horizontal
- Indicateur scroll bas : chevron animé (bounce)

### 5.7 Section Événements

```
┌─────────────────────────────────────────────┐
│  FOND NOIR                                  │
│                                             │
│            ÉVÉNEMENTS                       │   ← --text-h1
│                                             │
│  ┌────────┐  ┌────────┐  ┌────────┐        │
│  │Affiche │  │Affiche │  │Affiche │        │   ← Grille de cartes
│  │ HMF #1 │  │ HMS #1 │  │ HMS #2 │        │
│  └────────┘  └────────┘  └────────┘        │
│                                             │
└─────────────────────────────────────────────┘
```

- Événements à venir en premier, passés ensuite (badge "Passé")
- Chaque carte cliquable → page détail

### 5.8 Section Notre Histoire

```
┌─────────────────────────────────────────────┐
│  FOND BLUR (fond_hoppy_music.jpg)           │
│                                             │
│            NOTRE HISTOIRE                   │   ← --text-h1
│                                             │
│   Texte descriptif du collectif...          │   ← --text-body, max-width 680px
│                                             │
└─────────────────────────────────────────────┘
```

- Fond blur uniquement, **pas d'images** dans cette section
- Texte centré, largeur max 680px
- Possible symbole houblon coloré en décoration subtile

### 5.9 Section Réseaux sociaux

```
┌─────────────────────────────────────────────┐
│  FOND NOIR + DOODLE filigrane (5-10%)       │
│                                             │
│         SUIVEZ-NOUS                         │   ← --text-h1
│                                             │
│     [ feed Instagram / grille photos ]      │
│                                             │
│       Instagram    Facebook                 │   ← Icônes + liens
│                                             │
└─────────────────────────────────────────────┘
```

### 5.10 Footer

```
┌─────────────────────────────────────────────┐
│  FOND : --color-surface                     │
│                                             │
│  ┌──────────┬───────────┬──────────┐        │
│  │  LOGO    │  LIENS    │ CONTACT  │        │
│  │  Hoppy   │ Événements│ Email    │        │
│  │  Music   │ Histoire  │ Adresse  │        │
│  │          │ Boutique  │ Louvres  │        │
│  │  IG  FB  │ Contact   │ 95380    │        │
│  └──────────┴───────────┴──────────┘        │
│                                             │
│  ─── bande doodle séparateur (15-20%) ───   │
│                                             │
│  © 2024 Hoppy Music — Louvres, Val d'Oise  │   ← --text-caption
└─────────────────────────────────────────────┘
```

- 3 colonnes desktop, empilé mobile
- Séparateur : fine bande extraite des illustrations doodle

---

## 6. Animations & Transitions

### 6.1 Principe

Animations **subtiles** — fluidité avant tout, pas de spectaculaire.

### 6.2 Catalogue

| Élément                  | Animation                                   | Durée   | Easing       |
| ------------------------ | ------------------------------------------- | ------- | ------------ |
| **Apparition au scroll** | Fade-in + translateY (20px → 0)             | 600ms   | ease-out     |
| **Hover boutons**        | translateY(-1px) + opacité                  | 200ms   | ease         |
| **Hover cartes**         | translateY(-4px) + box-shadow               | 200ms   | ease         |
| **Menu mobile**          | Slide-in depuis la droite                   | 300ms   | ease-out     |
| **Header scroll**        | Fond transparent → semi-transparent + blur  | 300ms   | ease         |
| **Indicateur scroll**    | Bounce vertical (loop)                      | 1500ms  | ease-in-out  |
| **Chargement images**    | Fade-in depuis opacity 0                    | 400ms   | ease         |

### 6.3 Règles

- `prefers-reduced-motion: reduce` → désactiver toutes les animations sauf transitions de navigation
- Pas de parallax, pas de scroll-jacking
- Animations au scroll : déclenchement unique (pas de re-trigger)

---

## 7. Grille & Layout

### 7.1 Container

| Propriété     | Valeur                  |
| ------------- | ----------------------- |
| Max-width     | 1200px                  |
| Padding       | `0 var(--space-lg)`     |
| Centrage      | `margin: 0 auto`        |

### 7.2 Breakpoints

| Nom        | Valeur     | Colonnes | Navigation       |
| ---------- | ---------- | -------- | ---------------- |
| `mobile`   | < 640px    | 1        | Menu burger      |
| `tablet`   | 640–1024px | 2        | Menu burger      |
| `desktop`  | > 1024px   | 3        | Barre fixe       |

---

## 8. Inventaire des assets

### 8.1 Fichiers

| Fichier                              | Type          | Usage                                    |
| ------------------------------------ | ------------- | ---------------------------------------- |
| `HOPPY_MUSIC_Logo.png`               | Logo          | Hero, footer, header                     |
| `symbole_hoppy_music.png`            | Symbole       | Favicon, nav, décoration                 |
| `fond_hoppy_music.jpg`               | Background    | Sections fond blur                       |
| `affiche_hoppy_music_festival.jpg`   | Affiche       | Carte événement HMF                      |
| `affiche_hoppy_music_session.jpg`    | Affiche       | Carte événement HMS                      |
| `affiche_standard.jpg`               | Affiche       | Visuel générique Hoppy Music             |
| `illustration_1.png`                 | Doodle        | Format paysage — séparateurs, fonds      |
| `illustration_2.png`                 | Doodle        | Format portrait — séparateurs, fonds     |
| `HMSIMG12x.jpg`                      | Photo         | Public / ambiance (face painting)        |
| `HMSIMG2.jpg`                        | Photo         | Duo acoustique plein air                 |
| `HMSIMG32x.jpg`                      | Photo         | Guitariste scène, éclairage coloré       |
| `HMSIMG42x.jpg`                      | Photo         | Duo guitare + chant, éclairage bleu      |
| `HMSIMG52x.jpg`                      | Photo         | Chanteur bras ouverts, éclairage violet  |
| `HMSIMG62x.jpg`                      | Photo         | DJ aux platines, éclairage bleu          |

### 8.2 Icônes doodle extractibles

Éléments individuels pouvant être isolés depuis les illustrations :

| Icône                | Contexte d'usage                |
| -------------------- | ------------------------------- |
| Guitare              | Artistes / musique              |
| Chopes qui trinquent | Bières / partenaires brasseurs  |
| DJ aux platines      | Programmation / DJ sets         |
| Enceintes            | Son / technique                 |
| Vinyle               | Playlist / ambiance             |
| Chapiteau            | Infos pratiques / lieu          |
| Foodtruck            | Restauration                    |
| Bannière "LIVE"      | Badge événement en cours        |
| Notes de musique     | Décoration générale             |
| Main rock 🤘         | Décoration / CTA                |

---

## 9. Variables CSS — Récapitulatif

```css
:root {
  /* Couleurs */
  --color-bg: #181617;
  --color-text: #FBFCFB;
  --color-text-secondary: #A0A0A0;
  --color-surface: #2A2829;
  --color-border: #3A3839;
  --color-glass: rgba(251, 252, 251, 0.10);
  --color-overlay-light: rgba(251, 252, 251, 0.60);
  --color-overlay-dark: rgba(24, 22, 23, 0.50);

  /* Typographie */
  --font-heading: 'Reem Kufi', sans-serif;
  --font-body: 'Quattrocento Sans', sans-serif;
  --font-session: 'Permanent Marker', cursive;

  --text-hero: 72px;
  --text-h1: 48px;
  --text-h2: 32px;
  --text-h3: 24px;
  --text-body: 16px;
  --text-small: 14px;
  --text-caption: 12px;
  --text-session: 40px;

  /* Espacement */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 48px;
  --space-2xl: 80px;
  --space-3xl: 120px;

  /* Radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 16px;
  --radius-full: 9999px;

  /* Transitions */
  --transition-fast: 200ms ease;
  --transition-normal: 300ms ease;
  --transition-slow: 600ms ease-out;
}
```

---

## 10. À définir ultérieurement

| Élément                     | Statut       | Notes                                              |
| --------------------------- | ------------ | -------------------------------------------------- |
| Page détail événement       | À designer   | Layout affiche + programmation + infos pratiques    |
| Boutique                    | Plus tard    | Composants produit, panier, checkout               |
| Formulaire de contact       | À designer   | Style des inputs sur fond sombre                   |
| Galerie photos              | À designer   | Lightbox, grille masonry ou standard               |
| Intégration Payload CMS     | À configurer | Collections : événements, artistes, produits       |
| SEO & métadonnées           | À définir    | Open Graph, Twitter Cards, structured data         |
| Favicon & PWA               | À produire   | Déclinaisons du symbole houblon                    |
