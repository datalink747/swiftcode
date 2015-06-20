---
layout: post
title:  "Les commentaires"
date:   2015-06-20 10:33:51
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /les-commentaires/
---

<div class="swift2">
	<p>Cette section a été relue et corrigée, elle prend maintenant en compte les modifications apportées avec <em>Swift 2</em>.</p>
</div>

**Utilisez les commentaires pour inclure du texte non-exécutable dans votre code, comme une note à vous même, pour ne pas oublier. Les commentaires sont ignorés par Swift lorsque que le code est compilé.**

Les commentaires dans Swift sont très similaires aux commentaires en C. Pour les commentaires sur une seule ligne, ils commencent par deux slashs (//) :

{% highlight swift %}
// Ceci est un commentaire
{% endhighlight swift %}

Vous pouvez aussi écrire des commentaires plus longs sur plusieurs lignes, qui commencent par un slash suivi d'une astérisque (/*) et finissent par une astérisque suivie d'un slash (*/) :

{% highlight swift linenos %}
/* Ceci est aussi un commentaire,
	mais écrit sur plusieurs lignes */
{% endhighlight swift linenos %}

Contrairement aux commentaires multi-lignes en C, les commentaires multi-lignes de Swift peuvent être imbriqués à l'intérieur d'autres commentaires multi-lignes. Vous devez simplement commencer votre commentaire comme s'il allait s'étendre sur plusieurs lignes et imbriquer chaque commentaires multi-lignes de la même façon :

<pre><gris>/* Ceci est le commencement de mon commentaire,
	il s'étend sur plusieurs lignes
/* Je peux imbriquer un nouveau commentaire à l'intérieur,
	qui peut lui-même s'étendre sur plusieurs lignes */
Ensuite je termine mon commentaire principal ici,
	Et je n'oublie pas de le fermer */</gris></pre>

Les commentaires multi-lignes imbriqués de la sorte permettent de commenter de larges blocs de code rapidement et facilement, même si le code contient déjà d'autres commentaires multi-lignes.
