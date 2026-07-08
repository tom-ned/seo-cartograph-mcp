# Livrable : WordPress (Gutenberg, Elementor, Divi)

Le livrable WordPress n'est pas un fichier : c'est un contenu structuré prêt à coller,
bloc par bloc, plus les réglages SEO. Identifier d'abord l'éditeur utilisé (demander, ou
déduire d'une page existante : classes `elementor-*`, `et_pb_*` pour Divi, sinon Gutenberg).

## Format de remise (quel que soit l'éditeur)

1. **Réglages de la page** : titre WP, slug, modèle de page conseillé (pleine largeur,
   sans sidebar — une landing avec sidebar fuit de partout), page parente si la
   hiérarchie d'URL le justifie (`/services/plombier-lausanne/`).
2. **Champs SEO** (Yoast ou Rank Math — donner les deux noms de champs) : titre SEO,
   meta description, requête cible principale. Si l'extension propose un score, prévenir
   que le vert n'est pas l'objectif — la SERP l'est.
3. **Le contenu bloc par bloc** — voir ci-dessous selon l'éditeur.
4. **Schema JSON-LD** : Rank Math et Yoast génèrent l'Organization de base ; le schema
   spécifique (LocalBusiness précis, FAQPage, Service) se colle dans un bloc HTML
   personnalisé en fin de page, dans `<script type="application/ld+json">`.
5. **Maillage** : liste des pages/articles existants à éditer avec, pour chacun, la
   phrase d'insertion complète contenant le lien (pas juste l'ancre — la phrase entière,
   prête à coller au bon endroit indiqué).

## Gutenberg (défaut)

Livrer une suite de blocs nommés, dans l'ordre, avec leur contenu exact :

```
[Bloc Titre H1] …
[Bloc Paragraphe] …
[Bloc Boutons — bouton primaire] Texte : « … » → lien : #contact
[Bloc Colonnes 3] Colonne 1 : … / Colonne 2 : … / Colonne 3 : …
[Bloc Citation] Témoignage : « … » — Prénom N., contexte
[Bloc HTML personnalisé] <script type="application/ld+json">…</script>
```

Astuce à transmettre : coller tout le texte brut d'un coup dans l'éditeur crée les
paragraphes automatiquement ; les blocs spéciaux (boutons, colonnes, FAQ) se montent
ensuite. Si le thème a des patterns (sections préconçues), dire lesquels utiliser.

## Elementor

Structurer par sections/widgets : `[Section pleine largeur — fond clair] > [Widget
Titre H1] > [Widget Texte] > [Widget Bouton]`. Nommer les widgets Elementor exacts
(Heading, Text Editor, Button, Icon Box pour les bénéfices, Testimonial, Toggle/Accordion
pour la FAQ — l'accordéon FAQ d'Elementor Pro génère le schema FAQPage tout seul, le
signaler pour éviter le doublon de schema).

## Divi

Même logique avec les modules Divi : Section > Row > Modules (Texte, Blurb pour les
bénéfices, Témoignage, Toggle pour la FAQ, Bouton). Rappeler de désactiver titre et
sidebar par défaut dans les réglages de page Divi.

## Publication automatique (connecteur ED)

Si le site WordPress du client est connecté à la plateforme app.tnedjar.com (connecteur
WordPress d'ED), proposer de créer la page en brouillon directement via la plateforme
plutôt que par copier-coller — puis relecture humaine et publication manuelle. Ne jamais
publier en ligne sans validation explicite de l'utilisateur.
