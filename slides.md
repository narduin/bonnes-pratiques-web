---
theme: apple-basic
download: false
highlighter: shiki
lineNumbers: false
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: fade-out
title: Bonnes pratiques du web
mdc: true
layout: intro
hideInToc: true
---

# Les bonnes pratiques du web

Accessibilité, sobriété, performances, sécurité, etc.

<div class="absolute bottom-10">
  <span class="font-700">
    <a href="https://www.nardu.in" rel="noreferer noopener">Nico,</a> Octobre 2023.<br>licence&nbsp;: <a href="https://creativecommons.org/licenses/by-nc/4.0/" rel="noreferer noopener" title="Détails de la licence">CC BY-NC</a>
  </span>
</div>

<!--
C'est parti !
-->

---
layout: default
hideInToc: true
---

# Sommaire

<Toc maxDepth="1"></Toc>

---
layout: intro-image-right
image: '/images/ours.jpg'
---

# l'Accessibilité Numérique
Pourquoi, pour qui, comment ?

---
layout: quote
hideInToc: true
---

# “&nbsp;La force du Web réside dans son universalité. L'accès de tous, quel que soit le handicap, en est un aspect essentiel.&nbsp;”
Tim Berners-Lee, Directeur du W3C et inventeur du World Wide Web

<!-- Accès universel (accessible) dès la création de l'outil -->

---
layout: fact
hideInToc: true
---

# 1 personne sur 5 est handicapée
La majorité des handicaps sont invisibles.

<!-- certains sont temporaires, certains arrivent avec l'âge -->

---
layout: quote
hideInToc: true
---

# “&nbsp;L’accessibilité numérique est un droit fondamental. C’est la possibilité pour toutes et tous d’utiliser les outils informatiques, quelle que soit leur façon d’y accéder.&nbsp;”
Access 42

---
layout: bullets
hideInToc: true
---

## L'accessibilité du Web englobe tous les handicaps qui affectent l'accès au Web, notamment&nbsp;:

- auditifs
- cognitifs
- neurologiques
- physiques
- psychologiques
- oraux
- visuels

---
layout: center
---

<div grid="~ cols-2 gap-4">
	<Youtube id="nw6-eDJXWzY" />
	<Youtube id="N9Q8oF0Lx2M" />
	<Youtube id="SlxIEPEC_Qc" />
	<Youtube id="LHUyDhutx80" />
</div>

---
layout: two-cols
---

# Bonnes pratiques

- HTML sémantique
- structure du contenu (titres)
- contrastes des couleurs
- taille des polices
- intitulés de formulaire
- messages d’erreur
- supprimer les animations/le mouvement (carousel, vidéo, scroll, etc.)
- écrire simplement et clairement

::right::

<img v-click="[4, 5]" class="absolute top-15 right-56 z-1" src="/images/cross.svg" width="20" height="20">

```text {all|2|3|4|none}
Erronée
└── h1 Titre principal
    ├── h2 Titre secondaire
    ├── h4 Titre niveau 4
    │   └── h5 Titre niveau 5
    ├── h2 Titre secondaire
    │   ├── h2 Titre secondaire
    │   ├── h3 Titre tertiaire
    │   │   ├── h4 Titre niveau 4
    │   │   │   └── h6 Titre niveau 6
    │   └── h3 Titre tertiaire
    └── h1 Titre principal
```

```text {0|all}
Correcte
└── h1 Titre principal
    ├── h2 Titre secondaire
    ├── h2 Titre secondaire
    │   └── h3 Titre tertiaire
    ├── h2 Titre secondaire
    │   ├── h3 Titre tertiaire
    │   ├── h3 Titre tertiaire
    │   │   ├── h4 Titre niveau 4
    │   │   │   └── h5 Titre niveau 5
    │   └── h3 Titre tertiaire
    └── h2 Titre secondaire
```

<!-- [HeadingsMap](https://addons.mozilla.org/fr/firefox/addon/headingsmap/) -->

---
layout: center
hideInToc: true
---

# les Formulaires
C'est si simple de faire n'importe quoi 🥰

---
layout: two-cols
---

<div class="form">
	<h2>Mauvais exemple&nbsp;:</h2>
	<form class="nul">
		<input type="text" placeholder="nom*">
		<input type="text" placeholder="email*">
		<button>Envoyer</button>
	</form>
</div>

::right::

<div class="form">
	<h2>Bon exemple&nbsp;:</h2>
	<span>Les champs marqués d'une astérisque * sont obligatoires.</span>
	<form class="cool">
		<label for="name">Nom*</label>
		<input id="name" type="text" placeholder="Jean" required>
		<label for="email">Email*</label>
		<input id="email" type="email" placeholder="jean@email.com" required>
		<button>Envoyer</button>
		<span class="error" v-click>L'email renseigné n'est pas valide.</span>
	</form>
</div>

<div class="absolute bottom-10">
	<a href="https://briefs.video/videos/what-happened-to-text-inputs/" rel="noreferer noopener">Qu'est-il arrivé au champ texte&nbsp;? <small>Vidéo en anglais.</small></a>
</div>

---
layout: center
---

# La réglementation

[Obligatoire à partir de Juin 2025](https://access42.net/transposition-directive-europeenne-ue-2019-882-accessibilite-produits-services/) pour tout nouveau site ou service web.

<!-- Reste 1 an pour sortir des projets inaccessibles -->

---
layout: intro-image-right
image: '/images/pierre.jpeg'
---

# Sobriété

Utiliser uniquement ce dont le site a besoin.

<!--
Autant en terme de fonctionnalités que de ressources.
Exemple T-shirt
-->

---
layout: center
---

Il n'y a pas (encore) de cadre légal mais il existe un référentiel&nbsp;: le <abbr title="Référentiel général d'écoconception de services numériques">RGESN</abbr>

---
layout: intro-image-right
image: '/images/brumm.avif'
---

# Performances

Compressions, optimisations, chargements…

---
layout: default
hideInToc: true
---

## Leviers

- Images
  - dimensionner correctement
  - compresser
  - conversion en format récent (webp, avif)
- Vidéos
  - compression
  - conversion (webm, av1)
- Fonts
  - compression
  - conversion (woff2)
- Code source
  - minification
  - compression (gzip, brotli)

<style>
	ul {
		font-size: 1rem;
	}
</style>

<!-- squoosh et/ou plugin WP -->

---
layout: intro-image-right
image: '/images/tigre.avif'
---

# Sécurité

Certificat, données clients, attaques…

<!-- De nombreux réglages sont déjà activés. À vous de ne pas faire n'importe quoi avec le backoffice. -->
---
layout: bullets
---

# Ressources

- [Référentiel général d’amélioration de l’accessibilité](https://accessibilite.numerique.gouv.fr/)
- [Référentiel général d'écoconception de services numériques](https://ecoresponsable.numerique.gouv.fr/publications/referentiel-general-ecoconception/)
- [Test de performances](https://pagespeed.web.dev/)
- HeadingsMap (extension navigateur)
  - [Firefox](https://addons.mozilla.org/fr/firefox/addon/headingsmap/)
  - [Chrome](https://chrome.google.com/webstore/detail/headingsmap/flbjommegcjonpdmenkdiocclhjacmbi) (le démon)
- [Vérificateur de contraste](https://coolors.co/contrast-checker)
- **D'autres nombreux outils et ressources sur [3-w.fr](https://3-w.fr/dev/outils.html)**

---
layout: end
class: text-center
---

Merci :)