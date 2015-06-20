---
layout: post
title:  "Alias de types"
date:   2014-06-04 21:36:42
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /alias-types/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Les _alias de types_ permettent de définir un nom alternatif pour un type existant. Vous définissez votre alias avec la fonction <code>typealias</code>.**

Les alias de types sont utiles quand vous souhaitez vous référer à un type existant en utilisant un nom qui est contextuellement plus approprié, par exemple quand vous travaillez sur des données possédants une taille spécifique et provenant d'une source extérieure :

{% highlight swift %}
typealias AudioSample = UInt16
{% endhighlight swift %}

Une fois l'alias du type défini, vous pouvez utiliser cet alias n'importe où, à la place de l'endroit original qui accueillait avant le type de la variable ou de la constante :

{% highlight swift linenos %}
var amplitudeMax = AudioSample.min
// amplitudeMax vaut maintenant 0
{% endhighlight swift %}

Ici, <code>AudioSample</code> a été défini comme un alias du type <code>UInt16</code>, ce qui est plus clair pour le milieu de la musique. Comme c'est un alias, appeler <code>AudioSample.min</code> revient en fait à appeler <code>UInt16.min</code>, ce qui donne à la variable <code>amplitudeMax</code> la valeur <code>0</code>.