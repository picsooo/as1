# Proposition — ESASOUD Welding & Cutting

## Direction artistique : « Forge noire »

**Concept** : un site immersif à dominante sombre qui évoque l'intérieur d'un atelier de soudage — fond anthracite profond, textures métalliques subtiles en arrière-plan, et éclats de lumière chaude (le jaune ESAB) qui rappellent l'arc de soudure dans l'obscurité. L'idée forte : un **slider plein écran cinématique** qui occupe 100 vh, avec des transitions fluides entre les slides (fade + léger parallaxe), accompagnées d'un grain métallique animé en overlay. Chaque slide raconte un volet de l'activité (expertise, produits, réseau national). Le résultat est un site qui respire la puissance industrielle tout en restant élégant et lisible — à l'opposé des sites de distributeurs surchargés de catalogues.

---

## Palette de couleurs

| Rôle | Couleur | Code | Usage |
|------|---------|------|-------|
| Fond principal | Charbon profond | `#0C0F14` | Body, sections sombres |
| Surface élevée | Acier foncé | `#161B24` | Cards, navbar, footer |
| Surface secondaire | Graphite | `#1E2530` | Hover states, sections alternées |
| Texte principal | Blanc cassé | `#F0F0F0` | Titres, paragraphes |
| Texte secondaire | Gris acier | `#94A3B8` | Légendes, labels, metadata |
| Accent primaire | Jaune ESAB | `#F7B500` | CTA, liens actifs, highlights (usage modéré) |
| Accent secondaire | Bleu soudure | `#3B82F6` | Liens secondaires, icônes techniques |
| Bordures | Acier poli | `rgba(255,255,255,0.08)` | Séparateurs, contours de cartes |
| Destructif | Rouge alerte | `#EF4444` | Erreurs formulaires |

**Règle** : le jaune `#F7B500` ne dépasse jamais 15 % de surface visible. Il intervient uniquement sur les boutons CTA, la barre de progression du slider, et les accents typographiques ponctuels.

---

## Typographie (Google Fonts)

| Rôle | Police | Graisse | Usage |
|------|--------|---------|-------|
| Titres display (hero) | **Bebas Neue** | 400 | Headlines du slider, titres de section en grand |
| Titres courants | **Inter** | 600–700 | H2, H3, noms de produits |
| Corps de texte | **Inter** | 400 | Paragraphes, descriptions, tableaux |
| Labels / metadata | **Inter** | 500 | Badges, étiquettes, navigation |

**Échelle typographique** : 14 / 16 / 18 / 24 / 32 / 48 / 72 / 96 px

```
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@400;500;600;700&display=swap');
```

Bebas Neue en majuscules naturelles pour les titres hero crée un impact industriel fort sans forcer un `text-transform: uppercase` générique.

---

## Structure des sections (index.html)

### Slide 1 — « Votre partenaire soudage en Algérie »
- Image : `main-slider-img.jpg` (plein écran, filtre sombre 60 %)
- Titre display en Bebas Neue 96 px
- Sous-titre en Inter 18 px
- CTA : « Découvrir nos solutions » (jaune ESAB)

### Slide 2 — « Représentant officiel ESAB »
- Image : `main-slider-img1.jpg`
- Titre + logo ESAB en texte stylisé
- Baseline : « Soudage · Coupage · Consommables · Accessoires »

### Slide 3 — « Assistance technique & formation »
- Image : `main-slider-img2.jpg`
- Texte : positionnement service/accompagnement
- CTA : « Contactez-nous »

### Slide 4 — « 5 agences, couverture nationale »
- Image : `welding_1.jpg`
- Carte simplifiée Algérie avec les 5 points
- CTA : « Trouver votre agence »

**Navigation slider** : indicateurs en barre horizontale fine (jaune ESAB), progression automatique 6s, pause au hover. Flèches latérales discrètes.

---

### Sections sous le slider

| # | Section | Contenu |
|---|---------|---------|
| 1 | **À propos** | Présentation ESASOUD + positionnement (accompagnement > vente) |
| 2 | **Nos gammes** | 4 cartes (Consommables, Soudage, Coupage, Accessoires) avec images catégories, hover reveal |
| 3 | **Produit vedette** | Caddy Arc 151i/201i — sélecteur de modèle, photo, specs clés, lien fiche PDF + CTA devis |
| 4 | **Nos partenaires** | Bandeau logos défilant (ESAB texte + Elbor, Swaty, GCE, Chemtal, Osborn, Bosch) |
| 5 | **Nos agences** | 5 cartes avec adresse, téléphones (liens `tel:`), horaires, lien Google Maps |
| 6 | **Contact** | Formulaire (nom, entreprise, email, téléphone, message) + confirmation JS |
| 7 | **Footer** | Coordonnées siège, liens rapides, mention légale |

---

## Éléments distinctifs

1. **Grain métallique animé** : un overlay SVG très subtil (noise texture, opacity 3-5 %) qui bouge lentement, donnant vie aux surfaces sombres sans alourdir.

2. **Ligne lumineuse** : un filet horizontal `#F7B500` de 2 px sépare les sections majeures — rappel de l'arc de soudure, fil conducteur visuel du site.

3. **Reveal au scroll** : les sections apparaissent avec un fade-in + translate-Y de 30 px, timing 400 ms ease-out, respectant `prefers-reduced-motion`.

4. **Cards « acier brossé »** : les cartes gammes ont un fond `#161B24` avec une bordure supérieure de 2 px en `#F7B500` au hover, et un léger éclat (gradient radial blanc 3 % en coin supérieur gauche) simulant un reflet métallique.

5. **Responsive mobile** : le slider conserve son plein écran à 390 px avec des titres réduits à 48 px. Les cartes gammes passent en colonne unique. La navigation devient un hamburger menu avec panneau latéral sombre.

---

## Ce qui distingue cette proposition

- **Pas un catalogue** : le site raconte une histoire (slider narratif) avant de montrer des produits.
- **Pas cliché industriel** : pas de bandes jaune/noir, pas de chanfreins, pas de textures rouille. L'industrie est évoquée par la profondeur sombre, la précision typographique et les éclats lumineux maîtrisés.
- **Mémorable** : le grain métallique animé et la ligne lumineuse créent une signature visuelle unique qu'aucun template ne reproduit.
- **Performant** : zéro librairie externe (hors Google Fonts), images lazy-loaded, CSS vanilla, JS minimal. Temps de chargement < 2s.

---

## Spécifications techniques

- **Grille** : max-width 1280 px, padding 24 px mobile / 48 px desktop, grille 12 colonnes CSS Grid
- **Breakpoints** : 390 px / 768 px / 1024 px / 1440 px
- **Animations** : transitions 200–400 ms, `cubic-bezier(0.16, 1, 0.3, 1)`, respect `prefers-reduced-motion`
- **Contrastes** : texte blanc `#F0F0F0` sur `#0C0F14` = ratio 15.2:1 (AAA), texte gris `#94A3B8` sur `#0C0F14` = ratio 7.1:1 (AAA)
- **Touch targets** : minimum 44 × 44 px sur mobile
- **Images** : `loading="lazy"`, `referrerpolicy="no-referrer"` pour les hotlinks esasoud.net
