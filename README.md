# Plugin Claude « seo-cartograph »

Le cockpit SEO piloté par votre IA : ce plugin connecte le **MCP SEO Cartograph**
(app.tnedjar.com) et installe les skills qui vont avec.

## Installation

```
/plugin marketplace add tom-ned/seo-cartograph-mcp
/plugin install seo-cartograph
```

À la première utilisation d'un outil Cartograph, Claude ouvre l'écran de connexion
OAuth : vous vous connectez avec votre compte app.tnedjar.com, et l'accès reste en
lecture (l'IA propose, vous validez dans le cockpit).

## Les skills

| Skill | Accès | Ce qu'il fait |
|---|---|---|
| `audit-express-seo` | **Gratuit** — sans compte | Audit d'une page en minutes, grille stricte, 5 corrections livrées prêtes à coller |
| `landing-page-seo` | **Gratuit** — données réelles avec le MCP | Landing page complète adaptée au périmètre tech : HTML, WordPress, Next/Nuxt/Astro, Webflow/Wix/Squarespace |
| `schema-markup` | **Gratuit** — sans compte | Génère et valide le JSON-LD (LocalBusiness, Product, FAQPage, Article…) prêt à coller |
| `audit-technique` | MCP requis | Audit technique complet sur le crawl réel — erreurs triées systémique/isolé, priorisées |
| `opportunites-seo` | MCP requis | Les 10 opportunités à meilleur retour sur effort, sur vos requêtes Search Console réelles |
| `brief-de-contenu` | MCP requis | Brief rédacteur calibré sur la SERP réelle : champ lexical GSC, plan, angle, maillage |
| `verdict-de-page` | MCP requis | Pour une URL : garder / rafraîchir / fusionner / supprimer, sur preuves |
| `chantier-maillage` | MCP requis | Chantier de maillage interne guidé — propositions justifiées envoyées dans le Netlinker |
| `bilan-seo-mensuel` | MCP requis | Le point mensuel court : GSC, GA4, positions, et les 3 actions du mois suivant |
| `rapport-client` | MCP requis | Le grand livrable client (marque blanche possible) : perf, positions, technique, opportunités |

## Le modèle

- **Vos données restent les vôtres** : le MCP lit votre compte (crawl, Search Console,
  GA4, positions) via OAuth, scoped à votre organisation, révocable en un clic.
- **L'intelligence est payée par votre abonnement Claude** — aucun compteur de tokens
  chez nous.
- **Les requêtes SERP live** consomment les crédits SERP inclus dans votre plan
  Cartograph (le solde est consultable à tout moment : outil `get_serp_credits`).

## Développement

Source de vérité : dossier `claude-plugin/` du repo cockpit. Toute évolution d'un skill
se fait ici puis se publie vers le repo public du marketplace.
