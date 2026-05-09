# GardenGeoDome — Website

Statische Website für **Jorinde Dehmel · GardenGeoDome** — Workshops zum
Bauen geodätischer Kuppeln in Freiburg.

Live: https://etzm.github.io/jorinde-website/

## Stack

- [Astro](https://astro.build) 6 (statische Generierung)
- Manrope (Body) + Fraunces / Caveat (Logo) — alle self-hosted via `@fontsource`
- Deploy: GitHub Actions → GitHub Pages

## Entwicklung

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # dist/
```

Pages liegen unter `src/pages/`, geteiltes Layout in `src/layouts/VariantB.astro`.
Bilder unter `public/images/preview/`.

## Deploy

Push auf `main` triggert `.github/workflows/deploy.yml` — Astro-Build via
`withastro/action@v3`, Upload via `actions/deploy-pages@v4`.

`astro.config.mjs` setzt `site` und `base` für den GitHub-Pages-Subpfad.
Beim Wechsel auf eine Custom Domain (z.B. `gardengeodome.com`):
1. `base` aus `astro.config.mjs` entfernen
2. `public/CNAME` mit der Domain anlegen
3. DNS-CNAME-Record auf `etzm.github.io`

## Credits

### Logo

Das Geodome-Glyph im Brand-Seal stammt von **Methadrone** vom
[The Noun Project](https://thenounproject.com/creator/Methadrone/) —
Icon "Geodesic Dome" (ID 11999), lizenziert unter Creative Commons BY 3.0.

Quelle: https://thenounproject.com/creator/Methadrone/

Implementierung: `src/components/BrandSeal.astro` — die Pfade des Original-SVG
sind eingebettet, mit konzentrischen Ringen und gebogenem Text gerahmt.

### Schriften

- [Manrope](https://fonts.google.com/specimen/Manrope) — Open Font License
- [Fraunces](https://fonts.google.com/specimen/Fraunces) — Open Font License
- [Caveat](https://fonts.google.com/specimen/Caveat) — Open Font License

### Fotos

Alle Workshop- und Projektfotos: © Jorinde Dehmel.

### Code

Astro-Scaffold ursprünglich aus dem [Astro Blog Template](https://github.com/withastro/astro/tree/main/examples/blog),
inzwischen vollständig durch Variant B (Triangulation) ersetzt.
