---
layout: post
title:  "Concaténer les chaînes et les caractères"
date:   2015-06-22 10:01:54
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /concatener-chaines-caracteres/
---

<div class="swift3">
	<p>Vous êtes dans un nouveau chapitre. Traduit directement depuis la dernière version en date de la documentation officielle de <em>Swift 2</em>.</p>
</div>

**Les valeurs des chaînes peuvent être ajoutées ensemble (ou *concaténées*) avec l'opérateur d'addition (`+`) pour créer une nouvelle chaîne.**

{% highlight swift linenos %}
let chaine1 = "salut"
let chaine2 = " toi"
var bienvenue = chaine1 + chaine 2
// bienvenue vau maintenant "salut toi"
{% endhighlight swift linenos %}

Vous pouvez aussi ajouter la valeur d'une chaîne à une variable de type `String` existante avec l'opérateur d'affectation et d'addition (`+=`) :

{% highlight swift linenos %}
var instruction = "regarde"
instruction += chaine2
// instruction vaut maintenant "regarde toi"
{% endhighlight swift linenos %}

Vous pouvez aussi ajouter un caractère à une variable de type `String` grâce à la méthode `append()` :

{% highlight swift linenos %}
let pointExclamation: Character = "!"
bienvenue.append(pointExclamation)
// bienvenue vau maintenant "salut toi!"
{% endhighlight swift linenos %}

>**Note :** Vous ne pouvez pas ajouter une chaîne ou un caractère à une variable de type `Character` existante, parce-que ce type de variable (ou de constante) ne doit contenir qu'un seul caractère uniquement.
