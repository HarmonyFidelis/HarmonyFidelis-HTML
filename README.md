# HTML et CSS
## 0 - Initialisation
Pour créer un site statique créer un dossier App et initié votre projet.
```code
git init                            // Initialise votre projet github
git remote add <URL>                // Associe votre projet à un repos github

npm yarn init                       // Initialise votre gestionnaire de paquet
npm yarn add <DEPENDANCE>           // Permet d'installez les dépendances de votre projet
```

---
## 1 - Architecture 
Créer votre architure fichiers.

```code
App
 |- public                          // Visible par le client
 |    |- index.html                 // Fichier d'entrer par le client (Page d'accueil)
 |    |- apple-touch-icon.png       // Icone
 |    |- favicon.ico                // Icone
 |    |- favicon.svg                // Icone
 |    |- manifest.json              // Information concernant le site
 |    |- sitemap.xml                // Carte de l'architecture du site
 | 
 |- src                             // Contient les fichiers anexes non visible par le client
 |    |- Assets                     // Contient le contenue media de la page
 |          |- styles
 |               |- style.css       // Feuille de style
 |          |- images
 |               |- image.jpg       // Image
 |          |- scripts
 |               |- script.js       // Fichier javaScript
 |    |- views
 |          |- Other.html           // Autres pages HTML
 |    |- Components
 |          |- Composant1.html      // Code ayant une fonction particuliere
 |    |- index.js                        // Fichier receptionnant tout les scripts.js
 | 
 |- node_modules
 |- .env
 |- .gitignore                      // Ignore l'envoi de fichier lourd(node_modules)ou sensible(.env) au repo
 |- package.json                    // Dépendance et information relative au projet
 |- yarn.lock                       // Dépendance et information relative au projet
```
---
## 2 - HEAD
Ajouter vos heads à vos pages html avec les informations nécessaires.

```code
-- name.html --

<!doctype html>
<!-- XMNLS et XML permmette de stocker des informations utile à la comprehension du code -->
<html xmnls:site="https://www.harmonyfidelis.com/URI/home.html" xml:lang="fr" lang="fr">
<head>
   <!-- CARACTERE --> 
  <meta charset="utf-8"><!--Caracteres speciaux-->

  <!-- COPYRIGHT-->
  <meta name="author" content="Jérémy Salettes-Wozniak">  <!--Auteur du code-->
  <meta name="copyright" content="Copyright proprietaire">  <!--Propietaire du code-->

  <!-- BASE-->
  <title>Titre de votre site</title> <!--Titre de votre page-->
  <meta name="description" content="description de votre site en 160caracteres max"> <!--description contenue page-->
  <link rel="manifest" href="manifest.json"><!-- Progressive Web App (NOM APP / ICON / URL ) -->
  <link rel="canonical" href="https://www.harmonyfidelis.com/" /><!-- Origine d'une page en cas de doublon -->
  <link rel="sitemap" href="sitemap.xml" type="application/xml" /><!-- Sitemap du site-->
  <meta name="language" content="fr" /> <!-- Langue du contenu-->  
  <meta name="viewport" content="width=device-width, initial-scale=1"> <!--Responsive / Mise à l'echelle -->
  <meta name="robots" content="index,follow" /> <!-- Indique si le robot doit ou non indexer et suivre lien page-->


  <!-- CONTROLE -->
  <meta name="distribution" content="global"> <!--Destination : global=all / local="local" / UI="Intranet"-->
  <meta name="rating" content="general"> <!-- Definit le public concernait general / adult / safe for kids-->
  <meta http-equiv="pics-label" content="neutral"> <!-- Permet de filtrer contenue selon le contexte -->

  <!-- SOCIAL MEDIA-->
  <meta property="og:title" content="A Basic HTML5 Template">
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://www.harmonyfidelis.com/">
  <meta property="og:description" content="description de votre site en 160caracteres max">
  <meta property="og:image" content="image.png">
  <meta property="og:image:type" content="image/png" />
  <meta property="og:image:width" content="400" />
  <meta property="og:image:height" content="300" />
  <meta property="og:image:alt" content="description de l'image" />
  <meta property="og:locale" content="fr_FR" />
  <meta name="twitter:site" content="https://twitter.com/website" />
  <meta name="twitter:creator" content="https://twitter.com/SalettesJ" />

  <!-- ICONE-->
  <link rel="icon" href="/favicon.ico">
  <link rel="icon" href="/favicon.svg" type="image/svg+xml">
  <link rel="apple-touch-icon" href="/apple-touch-icon.png">




  <!-- STYLE & STYLE VENDOR -->
  <meta name="theme-color" content="#4285f4"> <!-- Modifie couleur interface navigateur avec celle du site-->
  <link rel="stylesheet" href="../src/assets/styles/style.css"> <!-- Fichier style.css-->
  <link rel="stylesheet" href="../src/assets/styles/print.css" media="print"> <!-- Autre fiche de style spécifique-->
  <link rel="stylesheet" href="specific.css" media="print and (feature)"> <!-- Si la condition est vrais-->

  <link
	rel="stylesheet"
  href="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
  integrity="sha384-HSMxcRTRxnN+Bdg0JdbxYKrThecOKuH5zCYotlSAcp1+c8xmyTe9GYg1l9a69psu"
  crossorigin="anonymous"
  />
</head>
<body></body>
</html>
```
---
## 3 - BODY
Votre body contiendra l'architecture de votre site.


```code
-- Architecture --
<header></header>                   // Architectural: Entete du site
<nav></nav>                         // Architectural: Navigation
<main></main>                       // Architectural: Principal
<footer></footer>                   // Architectural: Bas de page
<aside><aside>                      // Architectural: Contenue indirect
<div></div>                         // Architectural: Bloc conatainer
<dialog></dialog>                   // Architectural: Boite de dialogue
<template></template>               // Architectural: Contenu HTML qui ne doit pas être affiché mais instancier en JS
<slot></slot>                       // Architectural: Emplacement ou afficher du contenu dynamique

<div class="nom_class"></div>       // Class: Permet d'appeler des .class
<div class="nom_class"></div>
<div class="nom_class"></div>

<div class="nom_id"></div>          // ID : Permet d'appeler un #id
```
```
-- Textuelle -- 
<!-- Commentaire -->                // Textuel - Un commentaire.
<br>                                // Textuel - Saut de ligne.
<b>gras</b>                         // Textuel - Gras
<strong>gras important</strong>     // Textuel - Gras SEO TRES IMPORTANT
<i>italique</i>                     // Textuel - Italic    
<em>italic  important</em>          // Textuel - Italic SEO IMPORTANT
<mark>Surlignement</mark>           // Textuel - Surligne le texte SEO PEU IMPORTANT
<s>Barrer</s>                       // Textuel - Barrer le texte
<u>Soulignement</u>                 // Textuel - Soulignement du texte
<del>mot supprimer</del>            // Textuel - indique que le mot est supprimer
<ins>mot ajouter</ins>              // Textuel - indique que le mot est ajouter

<code>functioName()</code>          // Textuel - Code textuelle
<kbd>Ctrl</kbd>                     // Textuel - Touche clavier
<samp>Keyboard not found</samp>     // Textuel - Resultat produit d'un programme
<var>X</var>                        // Textuel - Variable en mathématique
<sub>2</sub>                        // Textuel - Texte plus petit en bas(formule)
<sup>2</sup>                        // Textuel - Texte plus petit en haut(puissance)
<time datetime="20:00">20:00</time> // Textuel - Definis une heure
<math>2 + 2</math>                  // Textuel - Langage mathématique (Tex)

<h1>Titre de niveau 1</h1>          // Textuel - Titre de niveau 1 SEO
<h2>Titre de niveau 2</h2>          // Textuel - Titre de niveau 2 SEO
<h3>Titre de niveau 3</h3>          // Textuel - Titre de niveau 3 SEO
<h4>Titre de niveau 4</h4>          // Textuel - Titre de niveau 4
<h5>Titre de niveau 5</h5>          // Textuel - Titre de niveau 5
<h6>Titre de niveau 6</h6>          // Textuel - Titre de niveau 6
<hgroup>                            // Textuel - Contient plusieurs titres
    <h1>Titre</h1>
    <h2>Sous-titre</h2>
</hgroup>


<p>Un paragraphe</p>                // Textuel - Paragraphe sur une ligne.
<pre>Un paragraphe</pre>            // Textuel - Paragraphe prenant en compte les retour à la ligne.
<abbr title="abreaviation">abbr</abbr> // Textuel - Donne le titre complet de l'abreviation
    

<ol>                                // Textuel - Liste ordonnée
  <li>Liste ordonnée</li>
  <li>Liste ordonnée</li>
</ol>

<ul>                                // Textuel - Liste non-ordonnée
  <li>Liste non-ordonnée</li>
  <li>Liste non-ordonnée</li>
</ul>

``` 
```
-- Media --
<a href="./other.html">A</a>         // Media - Lien vers un autre fichier
<a href="https://">A</a>             // Media - Lien vers une url
<a href="#id">A</a>                  // Media - Lien vers un id interne à la page
<a href="mailto:test@test.com">A</a> // Media - Lien vers un mail 
<a href="tel:+123456789">A</a>       // Media - lien vers un numero de telephone
<a href="" download="image.png">A</a>// Media - lien vers un telechargement

<data value="100">Objet</data>       // Media - Definit une valeur à un mot / objet

<!-- Permet à une ressource externe d'être interprétée comme une image, -->
<object type="application/pdf" data="/media/examples/fichier.pdf">
	<!-- Permet d'ajouter des parametre à un objet -->
	<param name="" value="">
</object>

<audio src="./music.mp3"></audio>    // Media - Lecteur audio

<video controls src="./video.mp4">   // Media - Lecteur video
  <track default kind="captions"     // Media - Piste audio de la video
  srclang="en" src="./audio.vtt" />
</video>


<img src="./image.svg" alt="decrit"> // Media - Image

// Media - Dessin vectoriel (Préférence à canvas)
<svg width="300" height="100">   
  <rect width="200" height="50" style="fill:rgb(255,0,0);"/>
</svg>

// Media - Dessin pixel
<canvas id = "canvas" width = "100" height = "100"></canvas>


```

```
-- Tableau -- 
<table>                              // Tableau -- Définit un tableau
<caption>                            // Tableau -- Définit une legende(descriptif) du tableau
<thead>                              // Tableau -- Définit l'entete d'un tableau
<tbody>                              // Tableau -- Définit le corp du tableau
<tfoot>                              // Tableau -- Définit le bas du tableau
<tr>                                 // Tableau -- Définit un ligne 
<th>                                 // Tableau -- Définit l'entete
<th scope="row">                     // Tableau -- Définit l'entete de la ligne
<th scope="col">                     // Tableau -- Définit l'entete d'un colonne
<td>                                 // Définit -- Définit les cellules d'une colonne
<colgroup>                           // Tableau -- Définit un groupe à selectionner
<col>                                // Tableau -- Selectionne une colonne
<col span="2">                       // Tableau -- Selectionne deux colonne

<table>
    <caption>Council budget (in £) 2018</caption>
    <thead>
        <tr>
            <th>Items</th>
            <th scope="col">Expenditure</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Donuts</th>
            <td>3,000</td>
        </tr>
        <tr>
            <th scope="row">Stationery</th>
            <td>18,000</td>
        </tr>
    </tbody>
</table>

<table>
    <caption>Superheros and sidekicks</caption>
    <colgroup>
        <col>
        <col span="2" class="batman">
        <col span="2" class="flash">
    </colgroup>
    <tr>
        <td></td>
        <th scope="col">Batman</th>
        <th scope="col">Robin</th>
        <th scope="col">The Flash</th>
        <th scope="col">Kid Flash</th>
    </tr>
    <tr>
        <th scope="row">Skill</th>
        <td>Smarts</td>
        <td>Dex, acrobat</td>
        <td>Super speed</td>
        <td>Super speed</td>
    </tr>
</table>
```

```
-- Script et iframe --
<noscript>Votre navigateur ne prend pas en charge les scripts</noscript>

// script javascript
<script src="javascript.js"></script>

// module javascript
<script type="module" src="main.mjs"></script>

// En cas de non prise en charge de module
<script nomodule src="fallback.js"></script>

// Ajout de contenu externe
<iframe width="560" height="315" src="https://harmonyfidelis.com/"></iframe>
<iframe width="560" height="315" src="./otherHTML"></iframe>
<iframe width="560" height="315" src="https://sketchfab.com/models/465fd961faae40518101c96c63db6b46/embed"></iframe>

<embed type="video/webm" src="/media/cc0-videos/flower.mp4" width="250" height="200">
```

```
-- Article --
<article>
  <h1>Titre de niveau 1</h1>
  <section id="introduction">
    <h2>Titre de niveau 2</h2>
    <p>Un paragraphe</p>
  </section>
  <section id="content">
    <h2>Titre de niveau 2</h2>
    <p>Un paragraphe</p>
  </section>
  <section id="summary">
    <h2>Titre de niveau 2</h2>
    <p>Un paragraphe</p>
  </section>
</article>

```

```code
-- Formulaire --
<button>click me</button>         // Formulaire - Button ecoutable(addEventListener)
<input type="button" value="">    // Formulaire - Equivalent à button 
<input type="submit">             // Formulaire - Permet d'envoyer des données d'un formulaire
<input type="checkbox">           // Formulaire - Permet de checked acompagnez d'un label
<input type="radio">              // Formulaire - Permet de selectionner une option
<input type="color">              // Formulaire - Permet de selectionner une couleur
<input type="date">               // Formulaire - Permet de rentrer une date
<input type="datetime-local">     // Formulaire - Permet de rentrer une date et une heure
<input type="time">               // Formulaire - Permet de saisir une heure
<input type="month">              // Formulaire - Permet de rentrer une année et un mois
<input type="week">               // Formulaire - Permet de d'afficher un calendrier pour selectionner date
<input type="email">              // Formulaire - Permet de rentrer une email
<input type="search">             // Formulaire - Permet de saisir des termes de recherche
<input type="file">               // Formulaire - Permet de choisir un fichier 
<input type="image" src="./img">  // Formulaire - Permet d'afficher une image comme button
<input type="number">             // Formulaire - Permet de saisir un nombre
<input type="text">               // Formulaire - Permet de saisir du texte
<input type="tel">                // Formulaire - Permet de saisir un numero de telephone
<input type="url">                // Formulaire - Permet de saisir un url
<input type="password">           // Formulaire - Permet de saisir de maniere confidentielle
<input type="range">              // Formulaire - Permet de faire une selecteur sous forme de barre
<input type="reset">              // Formulaire - Permet de reinitialiser la page
<input type="hidden">             // Formulaire - Masque l'input
 
<label for="id">                  // Formulaire - Legende d'un input
<input name="id" id="id">         // Formulaire - Input 

<input list="s-flavors" />
<datalist id="flavors">           // Formulaire - Permet de presenter des valeur possible
    <select>
        <optgroup label="Best">
            <option value="Chocolate">
            <option value="Coconut">
        </optgroup >
        <option value="Mint">
        <option value="Strawberry">
        <option value="Vanilla">
    </select>
</datalist>

```

```code
-- Adresse --
<adress>
  <a href="mailto:test@test.com">test@test.com</a><br>
  <a href="tel:+13115552368">06.XX.XX.XX.XX</a>
</adress>

```

```
-- Figure et Figcaption--
<figure>
    <img src="./image.png" />
    <figcaption>Description</figcaption>
</figure>

```
```
-- Definition --
<dl>                                // Représente une liste de description
    <dt>Mot à définir</dt>          // Mot a definir
    <dd>Définition du mot</dd>      // Definition du mot

    <dt>Mot à définir</dt>
    <dd>Définition du mot</dd>
</dl>

<p><dfn>Mot à définir :</dfn> définition du mot</p>
```
```
-- Citation -- 

<q cite="source">phrase cité</q>

<figure>
    <blockquote cite="https://">
        <p>Paragraphe</p>
    </blockquote>
    <figcaption>—Artist Name, <cite>Livre</cite></figcaption>
</figure>
```
```
-- barre de progression --
<label for="fuel">Fuel level:</label>
<meter id="fuel" min="0" max="100" low="33" high="66" optimum="80" value="50"></meter> // Barre statique


<label for="file">File progress:</label>
<progress id="file" max="100" value="70"> 70% </progress>  // Barre dynamique
```
```
-- Carte clickable -- 

<map name="exemple-map-1">
  <area shape="rect" coords="0,0 200,200" href="https://developer.mozilla.org" target="_blank" alt="Page d'accueil MDN" />
  <area shape="default" />
</map>
<img usemap="#exemple-map-1" src="https://via.placeholder.com/350x150">

```
```
<!-- Masquer un contenu -->
<details>
    <!-- Text qui permettre d'afficher le contenu -->
    <summary>Afficher le contenu</summary>
	<img src="https://transpire.me/wp-content/uploads/2019/05/transhumanism_45457678.jpg">
	<h3>Humanity+</h3>
</details>
```
