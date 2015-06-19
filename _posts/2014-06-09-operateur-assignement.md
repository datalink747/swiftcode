---
layout: post
title:  "L'opérateur d'assignement"
date:   2014-06-09 23:49:42
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /operateur-assignement/
---

**L'opérateur d'assignement (<code>a = b</code>) initialise ou met à jour la valeur de <code>a</code> avec la valeur de <code>b</code>. La partie à gauche de l'opérateur prend la valeur de la partie à sa droite :**

{% highlight swift linenos %}
let b = 10
var a = 5
a = b
// a est maintenant égal à 10
{% endhighlight swift linenos %}

Si la partie droite de l'assignement est un tuple avec plusieurs valeurs, ses éléments peuvent être décomposés à l'intérieur de multiples contantes ou variables à la fois :

{% highlight swift linenos %}
let (x, y) = (1, 2)
// x est égal à 1, et y est égal à 2
{% endhighlight swift linenos %}

Contrairement à l'opérateur d'assignement en C et en Objective-C, l'opérateur d'assignement du langage Swift ne se retourne aucune valeur. Le bout de code ci-dessous n'est pas valide :

{% highlight swift linenos %}
if x = y {
    // Ce n'est pas valide, x = y ne retourne aucune valeur
}
{% endhighlight swift linenos %}

Cette fonctionnalité empêche l'opérateur d'assignement d'être utilisé accidentellement alors que l'opérateur d'égalité est attendu. En rendant invalide l'opération <code>if x = y</code>, Swift vous aide à éviter ce type d'erreur dans votre code.