# Livrable : site builder (Webflow, Wix, Squarespace)

Pas d'accès code : le livrable est un **plan de montage** si précis que l'utilisateur (ou
son webmaster) n'a aucune décision à prendre — uniquement des gestes à faire dans
l'interface. La moindre ambiguïté (« ajoutez une section attrayante ») rend le livrable
inutilisable ; chaque instruction nomme l'élément d'interface exact et donne le contenu
complet à coller.

## Format du plan de montage

Tableau séquentiel, une ligne par geste :

| # | Où | Geste | Contenu à coller |
|---|---|---|---|
| 1 | Pages > Nouvelle page | Créer la page, nommer « … », slug `…` | — |
| 2 | Section 1 (Hero) | Ajouter section + titre H1 | « … texte exact … » |
| 3 | Sous le H1 | Paragraphe | « … » |
| 4 | Bouton principal | Texte + lien vers #contact | « Demander un devis » |
| … | | | |

Terminer par les réglages SEO de la page (voir par builder) puis la checklist de
publication.

## Webflow

- Réglages SEO : Page Settings > SEO Settings (title, meta description) + Open Graph.
- Schema JSON-LD : Page Settings > Custom Code > Inside `<head>` tag — coller le
  `<script type="application/ld+json">` complet.
- H1 : vérifier le tag dans l'inspecteur de l'élément Heading (Webflow laisse choisir
  H1-H6 — le préciser à chaque heading du plan).
- La FAQ en accordéon nécessite une interaction : proposer la version simple
  (question en H3 + paragraphe) si l'utilisateur n'est pas à l'aise.

## Wix

- Réglages SEO : Paramètres de la page > Référencement (SEO) — title, description, slug.
- Schema : Paramètres de la page > Référencement > Balisage structuré (JSON-LD) — champ
  dédié, coller l'objet complet.
- Les sections Wix s'ajoutent par « Ajouter une section » : indiquer la catégorie de
  section du panneau Wix la plus proche (« Témoignages », « FAQ », « Contact ») pour
  partir d'un gabarit, puis remplacer chaque texte par le contenu fourni.

## Squarespace

- Réglages SEO : Paramètres de la page > SEO — SEO Title, SEO Description ; slug dans
  Paramètres généraux.
- Schema : Paramètres > Avancé > Injection de code (par page) — coller le script dans
  l'en-tête. (Sur les plans sans injection par page, le signaler et livrer quand même le
  script pour l'injection globale conditionnelle ou l'abandon du schema — sans bloquer le
  reste.)
- Construire avec des blocs (Texte, Bouton, Accordéon pour la FAQ — l'accordéon
  Squarespace 7.1 est natif).

## Limites à annoncer (une fois, sans dramatiser)

Les builders imposent leur vitesse de chargement et leur balisage : c'est acceptable pour
une landing, mais si la page devient stratégique et stagne, la version HTML autonome ou
CMS reste l'issue de secours. Le plan de maillage reste indispensable : lister les pages
existantes du site builder à éditer, avec la phrase contenant le lien.
