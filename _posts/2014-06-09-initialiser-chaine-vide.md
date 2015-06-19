---
layout: post
title:  "Initialiser une chaîne vide"
date:   2014-06-09 23:51:51
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /initialiser-chaine-vide/
---

**Pour créer une valeur de type <code>String</code> en tant que point de départ, vous pouvez assigner une chaîne vide à une variable ou initialiser votre instance directement avec cette syntaxe :**

{% highlight swift linenos %}
var chaineVide = ""
var autreChaineVide = String()
// Ces deux chaînes sont vides et sont équivalentes.
{% endhighlight swift linenos %}

Vous pouvez deviner si la valeur d’une chaîne est vide en utilisant la propriété booléenne <code>isEmpty</code> :

{% highlight swift linenos %}
if chaineVide.isEmpty {
    println("la chaine est vide")
}
{% endhighlight swift linenos %}