# ESASOUD Welding & Cutting — Site vitrine

Proposition « Forge noire » — site vitrine statique pour ESASOUD, représentant officiel ESAB en Algérie.

## Structure

```
├── index.html          ← Page d'accueil (slider, gammes, produit, agences, contact)
├── produit.html        ← Fiche produit Caddy Arc 151i / 201i
├── assets/
│   ├── css/style.css   ← Design system complet
│   ├── js/main.js      ← Slider, scroll reveal, formulaires
│   └── img/            ← Images (après download-images.sh)
├── vercel.json         ← Config Vercel (cleanUrls)
├── download-images.sh  ← Script de téléchargement des images
├── PROPOSITION.md      ← Direction artistique
└── README.md           ← Ce fichier
```

## Déploiement GitHub → Vercel

1. Créer un repo GitHub et pousser le projet
2. Connecter le repo sur [vercel.com](https://vercel.com)
3. Framework preset : **Other** (statique)
4. Build command : laisser vide
5. Output directory : `.` (racine)
6. Déployer

Les `cleanUrls` dans `vercel.json` permettent d'accéder à `/produit` sans `.html`.

## Images

Les images sont chargées en hotlink depuis `esasoud.net` (avec `referrerpolicy="no-referrer"`).

Pour passer en images locales :

```bash
bash download-images.sh
```

Puis remplacer les URLs dans les fichiers HTML (le script affiche les commandes sed).

## Points à valider avec le client

- [ ] E-mail de contact : `contact@esasoud.net` à confirmer
- [ ] Textes des gammes : descriptions génériques à valider
- [ ] Ajout d'autres fiches produits si souhaité
- [ ] Intégration d'un backend pour le formulaire de contact (Formspree, Netlify Forms, etc.)
- [ ] Logo officiel ESASOUD si disponible (actuellement en texte)
- [ ] Certificats / agréments à afficher si disponibles

## Technique

- HTML / CSS / JS vanilla — aucun framework, aucun build
- Google Fonts : Bebas Neue + Inter
- Responsive : testé à 390 px et 1440 px
- Accessibilité : contrastes AAA, focus visibles, alt propres, liens tel:
- Performance : lazy loading, pas de librairie externe
