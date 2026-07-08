# Livrable : framework JS (Next.js, Nuxt, Astro)

Le destinataire est un développeur (ou Claude Code dans le repo). Livrer du code qui
respecte les conventions du framework ET du projet — si on a accès au repo, regarder
d'abord comment les pages existantes sont construites (layout, composants UI, i18n,
conventions de style) et s'y couler ; ne pas imposer un style exogène.

## Principes communs

- **Le SEO d'une landing JS se joue au rendu serveur.** La page doit être SSG/SSR (jamais
  client-only) : contenu, title, meta et schema présents dans le HTML initial.
- **Un fichier de contenu séparé du composant** quand le projet a déjà ce pattern
  (constantes, CMS headless, collections Astro) : le texte livré doit être éditable sans
  toucher au JSX/template.
- **Découpage en sections** conformes au squelette du SKILL.md (Hero, Preuves, Offre,
  Témoignages, FAQ, CTA) — une section = un composant seulement si le projet fait déjà
  comme ça.

## Next.js (App Router)

- `app/[slug]/page.tsx` (ou le chemin i18n du projet) avec `export const metadata` :
  title, description, `alternates.canonical`, openGraph.
- Schema JSON-LD : `<script type="application/ld+json"
  dangerouslySetInnerHTML={{ __html: JSON.stringify(jsonLd) }} />` dans le composant page
  — l'objet `jsonLd` typé et rempli avec les vraies valeurs.
- Images via `next/image` avec `width`/`height` et `alt` fournis.
- Si le projet a un sitemap dynamique (`app/sitemap.ts`), indiquer la ligne à ajouter.

## Nuxt 3

- Page dans `pages/`, meta via `useSeoMeta()` (title, description, ogTitle…) et canonical
  via `useHead({ link: [{ rel: 'canonical', href }] })`.
- Schema via `useHead({ script: [{ type: 'application/ld+json', innerHTML: JSON.stringify(jsonLd) }] })`
  ou le module `nuxt-schema-org` s'il est installé (vérifier).
- S'assurer que la route est prérendue si le site est en mode hybride (`routeRules`).

## Astro

- Page `.astro` dans `src/pages/` ; le contenu dans le frontmatter ou une entrée de
  collection selon les conventions du projet.
- Meta dans le layout ou la page ; schema dans un `<script type="application/ld+json"
  set:html={JSON.stringify(jsonLd)}>`.
- Astro est statique par défaut : rien à faire côté rendu, mais vérifier que la page
  entre dans le sitemap (`@astrojs/sitemap` la prend automatiquement).

## Remise

(1) le(s) fichier(s) de code complets, (2) le fichier de contenu si séparé, (3) la liste
des images à fournir avec le composant d'image du framework prérempli, (4) le plan de
maillage : quelles pages existantes du repo modifier, avec la phrase d'insertion du lien,
(5) la commande de vérification locale (`npm run dev` + URL) et le rappel de contrôler le
HTML rendu (view-source) : title, meta et schema doivent y être sans JavaScript.
