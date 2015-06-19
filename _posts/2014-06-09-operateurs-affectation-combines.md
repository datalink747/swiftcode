---
layout: post
title:  "Opérateurs d'affectation combinés"
date:   2014-06-09 23:49:44
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /operateurs-affectation-combines/
---

**Comme en C, Swift possède des opérateurs d'affectation qui combinent le signe d'assignement (<code>=</code>) avec une autre opération. Voyons un exemple avec le signe de l'addition (<code>+</code>) :**

{% highlight swift linenos %}
var a = 1
a += 1    // a vaut maintenant 3
{% endhighlight swift linenos %}

L'expression <code>a += 2</code> est un raccourcis pour <code>a = a + 2</code>. L'addition et l'assignement sont combinés en un seul opérateur qui effectue les deux taches en même temps.

><u>Note :</u> L'opérateur d'affectation combiné ne retourne pas de valeur. Vous ne pouvez pas écrire <code>let b = a += 2</code>, pour cet exemple. C'est différent de l'opérateur d'incrémentation dont nous avons parlé plus haut.

Vous pouvez retrouver la liste complète des opérateurs d'assignement dans la partie *"Expressions"*.