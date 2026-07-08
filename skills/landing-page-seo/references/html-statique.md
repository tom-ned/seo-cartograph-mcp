# Livrable : page HTML autonome (site statique / sur mesure)

Produire UN fichier `.html` complet, prêt à déposer sur l'hébergement, sans dépendance
externe. Le client (ou son développeur) ne doit avoir qu'à le poser et créer les liens.

## Règles de construction

- **Un seul fichier** : CSS dans `<style>` en tête, pas de framework, pas de CDN, pas de
  webfont externe (font-family système : `-apple-system, 'Segoe UI', Roboto, sans-serif`).
  Un fichier autonome survit à tous les hébergements.
- **Mobile d'abord** : la page doit être impeccable à 375 px. Meta viewport, tailles de
  police relatives, CTA pleine largeur en mobile, aucun scroll horizontal.
- **Léger** : viser < 50 Ko HTML+CSS. Pas de JS sauf nécessité réelle (un menu burger ne
  justifie pas 200 lignes — un lien d'ancre suffit souvent sur une landing).
- **Images** : baliser `<img src="[IMAGE : description précise de ce qu'il faut fournir]"
  alt="..." width="..." height="..." loading="lazy">` — dimensions réservées (pas de CLS),
  alt rédigés, et une liste récapitulative des images à fournir en fin de livraison.
- **Accessibilité de base** : un seul H1, hiérarchie Hn sans trou, contrastes AA, labels
  sur les champs de formulaire, `lang` correct sur `<html>` (fr-CH, de-CH, en…).

## Head complet

```html
<title>… ≤ 60 caractères …</title>
<meta name="description" content="… ≤ 155 caractères …">
<link rel="canonical" href="https://domaine.tld/slug/">
<meta property="og:title" content="…">
<meta property="og:description" content="…">
<meta property="og:image" content="[IMAGE OG 1200x630 à fournir]">
```

## Schema JSON-LD

Dans un `<script type="application/ld+json">` avant `</body>` :

- Offre locale (artisan, commerce, service localisé) → `LocalBusiness` (ou sous-type
  précis : `Plumber`, `Electrician`, `LegalService`…) avec NAP complet, `areaServed`,
  `openingHours`, et `aggregateRating` UNIQUEMENT si les avis existent réellement.
- Service non localisé → `Service` + `Organization`.
- Produit → `Product` + `Offer` (prix réel, devise).
- FAQ présente → ajouter `FAQPage` avec les questions/réponses EXACTES de la page (Google
  compare ; un écart tue le rich snippet).

## Formulaire

Une landing statique n'a pas de backend : livrer le formulaire en HTML avec `action`
paramétrable et le signaler (`[ACTION FORMULAIRE : brancher Formspree, Brevo ou le
backend maison]`). Champs minimum : nom, moyen de contact, message. Chaque champ en plus
coûte des conversions — ne demander que ce qui sert à recontacter.

## Remise

Livrer dans cet ordre : (1) le fichier HTML complet, (2) la liste des images à fournir
avec dimensions, (3) le plan de maillage (pages sources + ancres), (4) l'instruction de
mise en ligne en deux lignes (où poser le fichier, penser au sitemap).
