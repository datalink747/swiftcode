---
layout: post
title:  "Opérateur d'union nil"
date:   2015-06-20 10:33:51
categories: ['Les opérateurs ']
author: Guillaume L.
comments: True
permalink: /operateur-union-nil/
---

<div class="swift2">
	<p>Cette section a été relue et corrigée, elle prend maintenant en compte les modifications apportées avec <em>Swift 2</em>.</p>
</div>

**L'*opérateur d'union nil* `(a ?? b)` déclare une optionnelle `a` si elle contient une valeur, ou retourne par défaut la valeur de `b` si `a` est `nil`. L'expression `a` est toujours du type optionnel. L'expression `b` doit coïncider avec le type qui est stocké à l'intérieur de `a`.**

L'*opérateur d'union nil* est présenté de façon raccourci pour le code suivant :

{% highlight swift %}
a != nil ? a! : b
{% endhighlight swift %}

Le code ci-dessus utilise l'opérateur conditionnel ternaire et force l'ouverture (`a!`) pour accéder à la valeur à l'intérieur de `a` quand `a` n'est pas `nil`, et à retourner `b` le cas échéant. L'*opérateur d'union nil* permet d'une façon plus élégante de combiner la vérification conditionnelle tout en dévoillant les valeurs d'une manière concise et plus simple à lire.

>**Note :** Si la valeur de `a` est non-nil, la valeur de `b` n'est pas prise en compte. C'est une évaluation en circuit court.

L'exemple suivant utilise l'opérateur d'union nil pour choisir entre une couleur par défaut et une couleur optionnelle sélectionnée par l'utilisateur :

{% highlight swift linenos %}
let couleurDefaut = "rouge"
var couleurUtilisateur: String? // nil par défaut

var couleurDefinitive = couleurUtilisateur ?? couleurDefaut
/* L'utilisateur n'a pas définit de couleur
couleurUtilisateur vaut nil
du coup couleurDefinitive est fixée à "rouge" */
{% endhighlight swift linenos %}

La variable `couleurUtilisateur` est définie en tant qu'optionnelle de type `String`, avec une valeur par défaut à `nil`. C'est parce-que `couleurUtilisateur` est du type optionnel que l'on peut utiliser ici l'opérateur d'union nil afin d'obtenir à coup sur une valeur pour `couleurDefinitive`.

Comme `couleurUtilisateur` est `nil`, l'expression `couleurUtilisateur ?? couleurDefaut` retourne la valeur de `couleurDefaut`, soit *"rouge"*.

Si vous assignez une valeur *non-nil* à `couleurUtilisateur` et utilisez l'opérateur d'union à nouveau, la valeur par défaut deviendra alors celle définie par l'utilisateur :

{% highlight swift linenos %}
couleurUtilisateur: "vert"
couleurDefinitive = couleurUtilisateur ?? couleurDefaut
/* couleurUtilisateur ne vaut plus nil
du coup couleurDefinitive est fixée à "vert" */
{% endhighlight swift linenos %}
