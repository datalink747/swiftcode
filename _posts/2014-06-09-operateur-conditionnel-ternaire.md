---
layout: post
title:  "Opérateur conditionnel ternaire"
date:   2014-06-09 23:49:46
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /operateur-conditionnel-ternaire/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**L'opérateur conditionnel ternaire est un opérateur spécial avec trois parties et qui prend la forme suivante : <code>question ? réponse1 : réponse2</code>. C'est raccourcis pour évaluer deux expressions en même temps avec une seule question. Si la question est <code>true</code>, il renvoie des valeurs pour <code>réponse1</code> et <code>réponse2</code>.**

L'opérateur conditionnel ternaire sert à raccourcir les bouts de code comme celui-ci :

{% highlight swift linenos %}
if question {
    reponse1
} else {
    reponse2
}
{% endhighlight swift linenos %}

Voici un exemple pour calculer la hauteur en pixel de la colonne d'un tableau. La colonne doit être 50 pixels plus haute que la hauteur de son contenu, uniquement si elle possède une en-tête, et 20 pixels plus haute si elle n'en possède pas :

{% highlight swift linenos %}
let hauteurContenu = 40
let enTete = true
let hauteurColonne = hauteurContenu + (enTete ? 50 : 20)
// hauteurColonne vaut maintenant 90
{% endhighlight swift linenos %}

C'est beaucoup plus court que la version sans opérateur conditionnel ternaire :

{% highlight swift linenos %}
let hauteurContenu = 40
let enTete = true
var hauteurColonne = hauteurContenu
if enTete {
    hauteurColonne = hauteurColonne + 50
} else {
    hauteurColonne = hauteurColonne + 20
}
// hauteurColonne vaut maintenant 90
{% endhighlight swift linenos %}

Le premier exemple utilise l'opérateur conditionnel ternaire pour régler correctement la valeur de <code>hauteurColonne</code> en une seule ligne de code. C'est beaucoup plus court que dans le second exemple, et ça évite d'initialiser <code>hauteurColonne</code> comme une variable.

L'opérateur conditionnel ternaire permet de raccourcir considérablement votre code dans ce type de cas précis. Prenez néanmoins conscience qu'il ne facilite pas forcement la lecture du code et pourra poser problème si vous travaillez à plusieurs sur le même projet.