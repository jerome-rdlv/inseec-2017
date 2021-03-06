---
title: INSEEC 2017

toc_footers:
  - <a href='https://rue-de-la-vieille.fr'>Me contacter</a>

includes:

search: true
---

# JavaScript

## Introduction

JavaScript est différent de Java. Attention, pour abréger JavaScript, utiliser « js », pas « java ».
Les informations qui suivent sont toutes relative à JavaScript dans un environnement bien particulier :
le navigateur web. Pour des informations sur JavaScript dans d’autres contextes
voir [NodeJS](https://nodejs.org/en/).

Dans une page web, le balisage est censé servir le *sens*, la *sémantique* : structurer le contenu.
Un paragraphe, une liste, un lien, une section, un entête, etc. Les feuilles de styles en
cascade (Cascading Style Sheets / CSS) définissent l’*apparence* de ce contenu et,
dans une certaine mesure, son comportement. La mise en page, la police de caractère, les couleurs,
tout ça relève des CSS. L’apparence des différents éléments du contenu au survol du curseur,
ou lorsqu’ils recoivent le focus, ou lorsqu’ils sont activés par un clic, tout ça relève aussi
des CSS.

JavaScript vient ajouter une gestion plus complète et complexe de *comportement* et
d’*interactivité* à la page. On tâchera de ne pas traiter les questions d’apparence et de
cantonner JavaScript à des changements d’état, par exemple changements de classe sur les
élément de la page, et on laissera aux CSS la possibilité d’y réagir ou non.

## Recommandations

Pour travailler efficacement, pour progresser plus rapidement et s’éviter des souffrances
inutiles :

* Faire afficher les extensions de fichiers dans l’explorateur de fichiers, quel qu’il soit
(*Options des dossiers* sous Windows, *Préférences du Finder* sous MacOS).
* Isoler les exercices dans un dossier spécifique et travailler dans un seul dossier à la fois.
* Travailler avec l’inspecteur Web ouvert.
* Vérifier la console à chaque changement.
* Désactiver le cache.

## Insérer du JavaScript

> JavaScript en ligne

```html
<script type="text/javascript">
    alert('Hello INSEEC!');
</script>
```

Pour insérer du JavaScript directement dans une page, on utilise la balise script.
Le JavaScript est inséré entre deux balises, `<script>` et `</script>`.

Ça s’appelle *JavaScript en ligne* ou *inlined JS*. Cette façon de procéder possède
des inconvénients. Si le même script est utilisé sur toutes les pages du site 
(ce qui est extrêmement fréquent), il est rechargé par le réseau à chaque chargement de page,
ce qui implique la latence d’une requête supplémentaire et de la bande passante.

> JavaScript externalisé dans le fichier `index.js`

```html
<script type="text/javascript" src="index.js"></script>
```

Alors on préférera insérer du JavaScript en pointant vers un fichier externe.

De cette façon il peut-être mis en cache par le navigateur et n’être chargé
qu’une seule fois pour tout le site.

## Exercices

### Base

```html
<!DOCTYPE html>
<html lang="fr-FR">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1"/>
    <title>JavaScript</title>
    <link type="text/css" rel="stylesheet" href="css/main.css">
</head>
<body>
<header>
    <h1>Base JavaScript</h1>
    <button class="navToggle">
        Menu
    </button>
</header>
<main>
    <p>
        Vivamus at pharetra diam…
    </p>
    <p>
        Aliquam turpis arcu, aliquam ac venenatis…
    </p>
</main>
<nav>
    <ul>
        <li>
            <a href="#">Accueil</a>
        </li>
        <li>
            <a href="#">À propos</a>
        </li>
        <li>
            <a href="#">Portfolio</a>
        </li>
        <li>
            <a href="#">Contact</a>
        </li>
    </ul>
</nav>
</body>
</html>
```

Les exercices sont basés sur ce HTML.

### Exercice 1

```js
alert('Hello INSEEC!');
```

La fonction [`alert`](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)
permet de créer une boîte de dialogue.
Pour appeler une fonction on ajoute les parenthèses à son nom.
Les paramètres d’une fonction sont placés entre ces parenthèses, et séparés par des virgules.
Ici, la fonction `alert` prend une chaîne de caractère en paramètre
(du texte entre guillemets).

> Créer une fonction personnalisée :

```js
function doSomething(param) {
    // Ici on fait quelque chose, par exemple…
    console.log(param);
}
```

> Et l’appeler :

```js
doSomething();
```

La fonction [`alert`](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)
est pré-définie par le navigateur. Mais on peut définir nos propres fonctions.

<div style="clear:both"></div>

> Commentaires :

```js
// Ça, c’est un commentaire, sur une ligne

/* Et ça aussi,
   mais attention à bien le refermer */
```

Il est possible d’ajouter des commentaires en JavaScript.

### Exercice 2

```js
console.log('Hello INSEEC!');
```

Pour afficher un message dans la console de l’inspecteur Web on utilise
l’objet `console` mis à disposition par le navigateur, et on appelle sa 
*méthode* `log` qui accepte un ou plusieurs paramètres. Une *méthode*
est une fonction spécifique à un objet. On accède aux méthodes d’un
objet grâce à l’opérateur `.`

Pour plus d’informations sur cette méthode, voir la
[`documentation`](https://developer.mozilla.org/en-US/docs/Web/API/Console/log)

### Exercice 3

```js
var choix = confirm('Afficher un message ?');
if (choix) {
    console.log('En v’la un message !');
}
```

Utiliser un dialogue de confirmation et n’afficher un message dans la console  
que si l’utilisateur clique sur OK.

`var` est un mot clé JS.  
`choix` est le nom de la variable (une boîte).  
La fonction `confirm` retourne vrai ou faux.  
`if` est une structure de contrôle.

<div style="clear:both"></div>

```js
if (test) {
    // Ce block est exécuté si test est vrai
}
else {
    // Ce block est exécuté si test est faux
}
```

Un bloc de code est contenu entre des accolades.

### Exercice 4

Voir [Insérer du JavaScript](#inserer-du-javascript).

### Exercice 5

```js
for (var i = 1; i <= 1000; i = i + 1) {
    console.log(i);
}
```

Créer une boucle `for` pour afficher les nombres de 1 à 1000.

Une boucle `for` est composée de trois expressions :

* Initialisation
* Condition
* Incrémentation

`for` est une autre structure de contrôle de JavaScript.

<div style="clear:both"></div>

```js
var i = 1;
while (i <= 1000) {
    console.log(i);
    i++;
}
```

La boucle `while` est une autre façon de faire des boucles en JavaScript,
une autre structure de contrôle. Elle s’utilise différemment et répond à
d’autres cas.

À droite l’équivalent de l’exercice 5 réalisé avec une boucle `while`. 

### Exercice 6

```js
function fibonacci(max) {
    var fib = [0, 1];
    for (var i = 2; i < max; i++) {
        fib[i] = fib[i - 2] + fib[i - 1];
    }
    return fib;
}

var resultat = fibonacci(20);
console.log(resultat);
```

Écrire dans la console les 20 premiers nombres de la suite de Fibonacci.

`fib` est un tableau. L’index des tableaux commence à 0.  
`fib[0]` pour accéder au premier élément.  
`return` pour renvoyer la valeur.

> Approximation du nombre d’or

```js
var fib = fibonacci(20);
console.log('Phi ~ '+ (fib[19] / fib[18]));
```

À noter que les nombres de la suite de Fibonacci permettent d’approcher le
[nombre d’or](https://en.wikipedia.org/wiki/Golden_ratio#Relationship_to_Fibonacci_sequence)
lorsqu’on divise le nombre obtenu au rang n par le nombre obtenu au rang n-1.

### Exercice 7

```js
function showMessage() {
    console.log('Bouton cliqué !');
}

var button = document.querySelector('.navToggle');
button.addEventListener('click', showMessage);
```
Afficher un message dans la console lorsque l’utilisateur clique sur le bouton « Menu ».

`document` est l’élément racine de la page, fourni par le navigateur.  
`querySelector` est une méthode de `document` qui prend un sélecteur CSS en paramètre.  
`addEventListener`  est une méthode de l’élément `button`.  
Au clic, on exécute la fonction `showMessage`.

<div style="clear:both"></div>

```js
var button = document.querySelector('.navToggle');
button.addEventListener('click', function () {
    console.log('Bouton cliqué !');
});
```

Cet exemple pourrait aussi s’écrire avec une fonction anonyme ou
*closure*. Dans ce cas on passe non plus le nom de la fonction en paramètre
mais directement la fonction elle-même.

### Exercice 8


```js
var button = document.querySelector('.navToggle');
button.addEventListener('click', function () {
    var body = document.querySelector('body');
    body.classList.toggle('nav-on');
});
```

Lorsque l’utilisateur clique sur le bouton « Menu »,
ajouter une classe « nav-on » à l’élément body.

`classList` est une propriété de l’élément `body`.  
`toggle()` est une méthode de la propriété `classList`.  
On accède à la propriété d’un objet grâce à l’opérateur `.`  
`toggle()` ajoute ou retire la classe selon qu’elle est présente ou pas.

### Exercice 9

```css
nav {
    display: none;
}

body.nav-on nav {
    display: block;
}
```

Masquage et affichage du menu.

On ne gère que l’interactivité (événement click) en JavaScript.
Le changement d’affichage est laissé à CSS grâce à la modification d’une classe.
Le menu est masque par défaut avec `display: none` et affiché lorsque
l’élément `body` possède la classe `nav-on`.

Le code JavaScript ne change pas par rapport à l’exercice 8.

### Exercice 10

```css
nav {
    background: black;
    color: white;
    height: 100%;
    padding: 1em 2em;
    position: absolute;
    right: 0;
}
```

À ce stade, il est possible d’afficher / masquer la navigation en cliquant sur le bouton menu.
C’est bien, mais c’est moche. On voudrait plutôt que le menu :

* Apparaisse en blanc sur noir semi transparent
* Apparaisse tout contre le bord droit de la page
* Prenne toute la hauteur de la page

### Exercice 11

```css
nav {
    height: 100%;
    position: absolute;
    right: 0;
    top: 0;
    transform: translateX(-100%);
    transition: transform 300ms;
}
body.nav-on nav {
    transform: translateX(0);
}
```

Au lieu d’afficher et masquer le menu avec `visibility: hidden`
ou `display: none`, on le pousse hors écran avec `transform: translateX(100%)`.

Ici la valeur `100%` s’exprime en fonction de la largeur de l’élément.
Il est donc décalé de 100% de sa largeur vers la droite. Lorsque
l’élément `body` possède la classe `nav-on`, alors on annule le
décalage en le repassant à 0 et le menu apparaît.

La propriété CSS `transition` est ensuite utilisée pour demander au navigateur
d’animer la propriété `transform` lorsque sa valeur change. On indique
la propriété, `transform`, que l’on souhaite animer suivie de la durée de
l’animation, ici `300ms` pour 300 millisecondes. Il est possible d’exprimer
cette durée en secondes, par exemple `2s`.

Pour animer plusieurs propriétés, il faut les séparer par des virgules,
par exemple `transform: opacity 200ms, scale 100ms;`.

À noter que pour des raisons de performances, on tâchera autant que possible
d’animer uniquement les propriétés `transform` et `opacity`. Ces deux
propriétés CSS sont les plus rapides à calculer pour le navigateur.

### Exercice 12

```html
<form action="mailto:jerome@rue-de-la-vieille.fr" method="post">
    <p>
        <label for="form_nom">Nom</label>
        <input type="text" name="nom" id="form_nom">
    </p>
    <p>
        <label for="form_email">Email</label>
        <input type="email" name="email" id="form_email">
    </p>
    <p>
        <label for="form_message">Message</label>
        <textarea name="message" id="form_message"></textarea>
    </p>
    <p>
        <button>Envoyer</button>
    </p>
</form>
```

Créer un formulaire de contact avec les champs suivants :

* Nom (champ texte)
* Email (champ email)
* Message (champ texte long)

Le formulaire doit être soumis par email
(il sera modifié au moment du cours PHP pour être envoyé au serveur, peut-être).

### Exercice 13

```js
(function () {
    var form = document.querySelector('form');
    form.addEventListener('submit', function (e) {
        var fields = ['nom', 'email', 'message'];
        for (var i = 0; i < fields.length; ++i) {
            var field = form.querySelector('[name="'+ fields[i] +'"]');
            if (field.value === '') {
                e.preventDefault();
                alert('Le champ '+ fields[i] +' est obligatoire');
                break;
            }
        }
    });
})();
```

Écouter la soumission du formulaire et la bloquer si un des champs n’est pas renseigné.

On récupère l’élément `form` et on place un écouteur dessus, pour l’événement `submit`.
On n’écoute pas l’événement `clic` du bouton de soumission parce que le formulaire
peut-être soumis par d’autres moyens, notamment une validation dans un des champs text
(appui sur la touche `[ENTER]` lorsqu’un des champs texte a le *focus*).

Lorsque le formulaire est soumis, on teste les champs un par un. Puisque le traitement
est identique pour chaque champ, on a recourt à une boucle pour ne coder le travail
qu’une seule fois :

* Récupération du champ à partir de son nom
* Test de la valeur saisie (`field.value === ''`)
* Annulation de la soumission si le champ est vide, affichage d’une erreur et sortie de la boucle


# WordPress

## Création des événements

Le site Siècle Digital présente une liste d’événements.
Ces événements ne sont ni *post* ni *page*, ce sont des contenus personnalisés. WordPress permet
de déclarer et d’administrer facilement des *types de contenus personnalisés* ou 
[`Custom Post Type`](https://codex.wordpress.org/Post_Types).

Pour ajouter la gestion des événements voulue on va donc :

1. Créer un nouveau type de post pour nos événements
1. Ajouter au menu le lien vers la liste de nos événements
1. Créer des templates qui permettront de personnaliser l’affichage (le balisage) des événements
1. Personnaliser les styles associés à ces templates pour nous rapprocher de l’affichage de
    [Siècle Digital](https://siecledigital.fr/evenements/)

### Création d’un Custom Post Type

> Dans `wp-content/mu-plugins/instance.php`

```php
<?php
register_post_type(
    'sd_event', // nom informatique unique de notre CPT,
    array(
        'label' => 'Événements', // nom humain de notre CPT, affiché dans l’administration,
        'public' => true, // permet d’activer les interfaces de gestion de nos événements
        'has_archive' => true, // permet d’activer la fonctionnalité page d’archive
        'supports' => array(
            'title',
            'editor',
            'thumbnail', // permet d’associer une image à nos événements
        )
    )
);
```

Un type de post personnalisé est un contenu. On veut découpler la définition de ce contenu
du thème pour que l’administrateur du site puisse changer de thème sans perdre son contenu.
On souhaite aussi éviter que l’administrateur puisse perdre son contenu en désactivant une extension (plugin)
par inadvertance. On va donc enregistrer notre type personnalisé dans un
[`mu_plugin`](https://codex.wordpress.org/Must_Use_Plugins)
(plugin obligatoire, indispensable, toujours chargé par WordPress, inaccessible dans l’interface de gestion des plugins).

Pour créer un `mu_plugin` on crée un dossier `mu-plugins` dans le dossier `wp-content`, donc à côté des
dossiers `themes` et `plugins`. Dans ce dossier, on place un fichier `instance.php` avec le
code d’enregistrement du nouveau type de post (fonction
[register_post_type](https://codex.wordpress.org/Function_Reference/register_post_type)).

Attention à distinguer le *nom informatique* utilisé par le système de WordPress, qui doit être
sans caractères spéciaux, sans espaces et unique, du *nom humain* affiché dans l’interface
d’administration. Comme le *nom informatique* doit être unique, on diminue les risques de collision
en le préfixant. Ici on utilise *sd_* soit les initiales de *Siècle Digital* suivi d’un « *_* »
(« underscore » ou « tiret bas » ou « blanc souligné » ou « tiret du 8 » pour les noobs
qui ne connaissent que Windows les pauvres).

À noter que le paramètre `has_archive` permet de faire apparaître la page d’archive au niveau de
l’interface de gestion des menus (faire « View all » ou « Afficher tout » pour trouver ça).

<aside class="warning">
    Pour que WordPress prenne bien en compte les nouvelles URL liées à notre
    nouveau type de contenu, il faut aller dans les Réglages des Permalinks
    et enregistrer la page, telle quelle. 
</aside>

### Création des templates

> Base pour le template d’archive

```php
<?php get_header() ?>
<?php do_action('sd_events_filters') ?>
<?php while (have_posts()): the_post() ?>
    <article>
        <h2><?php the_title() ?></h2>
        <p><?php echo get_the_date(get_option('date_format')) ?></p>
        <div><?php the_content() ?></div>
    </article>
<?php endwhile ?>
<?php get_footer() ?>

```

> Base pour le template single

```php
<?php get_header() ?>
<?php the_post() ?>
<div>
    <h1><?php the_title() ?></h1>
    <p><?php echo get_the_date(get_option('date_format')) ?></p>
    <div><?php the_content() ?></div>
</div>
<?php get_footer() ?>
```

Utiliser la [hiérarchie des templates de WordPress](https://wphierarchy.com/) et créer
les bons templates dans le thème enfant :

* Un template prenant en charge l’affichage de la liste des événements (donc entrée *Archive*)
* Un template prenant en charge l’affichage d’un événement tout seul (donc entrée *Singular Page*)

On ajoute, au début du template d’archive, un *hook* d’action pour qu’un plugin puisse plus tard
insérer ici le formulaire de recherche / filtrage des événements : `do_action('sd_events_filters')`.

Du code tiers — plugin ou mu-plugin — pourra alors exécuter ce que souhaité en
enregistrant une fonction sur ce *hook* avec `add_action('sd_events_filters', function () {})`.


## Affichage d’une date personnalisée

> Dans functions.php pour la période

```php
<?php
/**
 * Retourne la période Mois, Année d’une date ACF.
 * Fonctionne si le format d’enregistrement ACF est yymmdd.
 * @param string $name Nom du champ ACF
 */
function sd_get_period($name){
    $date = DateTime::createFromFormat('Ymd', get_field($name, false, false));
    if ($date) {
        $period = $date->format('F Y');
    }
    else {
        $period = '';
    }
    return $period;
}
```

> Toujours dans functions.php pour un format spécifique

```php
<?php
function sd_get_acf_date($name, $format = 'd F Y')
{
    $date = DateTime::createFromFormat('Ymd', get_field($name, false, false));
    if ($date) {
        $formatted = $date->format($format);
    }
    else {
        $formatted = '';
    }
    return $formatted;
}
```

> Dans le template

```php
<?php $period = sd_get_period('date_begin') ?>
<p><?php echo $period ?></p>

<span><?php echo sd_get_acf_date('date_begin', 'd m Y') ?>
```

La date de survenue des événements est affichée entre les événements dans la liste
des événements sur le modèle Siècle Digital.

Pour pouvoir formatter simplement cette date dans le format souhaité,
on va utiliser un hook sur la valeur de date retournée par ACF
pour la convertir en objet `DateTime` PHP.

On peut ensuite utiliser le second bloc de code dans le template pour
obtenir la valeur, comme avant, et la formatter comme voulu.

À ce stade, la période (par exemple « Novembre 2017 ») va apparaître
entre chaque article. Je vous laisse chercher comment n’afficher cette
période que lorsqu’elle change.

Pour formatter la date d’un champ ACF, on utilise la fonction
`sd_get_acf_date`. Elle prend en premier paramètre le nom du champ,
en second paramètre le format
(voir [PHP `date()`](http://php.net/manual/fr/function.date.php));

## Modifier l’ordre des événements

> Dans `functions.php` (question relative au thème, à l’affichage)

```php
<?php

add_action('pre_get_posts', function ($query) {
    // attention, vérifier qu’on est sur la bonne requête avant toute autre opération !
    if (!$query->is_main_query()) {
        return;
    }
});
```

Par défaut, WordPress affiche les événements par ordre décroissant de date de création.
Nous souhaitons faire afficher ces événements par ordre croissant de champ
ACF (le champ ACF dans lequel nous stockons la date de début).

Pour modifier l’ordre d’affichage, il faut modifier la requête WordPress qui
va chercher les événements dans la base de données. Pour modifier cette
requête, WordPress nous offre un *hook* parfait : 
[`pre_get_posts`](https://codex.wordpress.org/Plugin_API/Action_Reference/pre_get_posts)
dont la documentation est d’une grande aide.

Attention, avant de modifier la requête, de vérifier qu’on modifie la bonne.
Pour information, le *hook* `pre_get_posts` est appelé pour toutes les requêtes
de contenu de WordPress, donc pour la requête principale, mais aussi pour les
requêtes supplémentaires (*sidebar* par exemple) et les requêtes de l’administration.

On peut évacuer les cas non désirés en suivant le modèle de l’exemple de droite :
test et `return` si le résultat ne convient pas. Le mot clé `return` fait
ressortir de la fonction et la suite de la fonction n’est pas exécutée.

Toutes les requêtes de WordPress sont représentées par un objet de type
[`WP_Query`](https://codex.wordpress.org/Class_Reference/WP_Query). La
documentation de cet objet, de ses *propriétés* et de ses *méthodes*
devrait suffire pour modifier l’ordre des événements. Un indice quand même,
il va falloir ajouter une [`WP_Meta_Query`](https://codex.wordpress.org/Class_Reference/WP_Meta_Query)
à l’objet `WP_Query` pour activer l’ordre sur un champ meta (*custom field*).
ACF se contente de fournir une interface d’édition au système de champs meta. Les
noms de vos champs ACF sont également les noms de vos champs meta,
utilisables dans une `WP_Meta_Query`.

<aside class="notice">
    Les indications qui précèdent sont truffées de mots clés qui donnent
    de bons résultats dans un moteur de recherche.
</aside>

## Ajouter un lien sous l’extrait de post

> Dans `functions.php`

```php
<?php
add_filter('the_excerpt', function ($exercpt) {
    $exercpt = $exercpt . '<a class="more-link" href="'. get_the_permalink() .'">Lire plus</a>';
    return $exercpt;
});
```

On se branche sur le *hook* `the_excerpt` et on ajoute
le lien à la valeur transmise (on modifie cette valeur,
l’extrait du post, grâce au *hook* de type filtre).