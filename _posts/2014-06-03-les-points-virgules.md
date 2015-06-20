---
layout: post
title:  "Les points virgules"
date:   2015-06-20 9:54:12
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /les-points-virgules/
---

<div class="swift2">
	<p>Cette section a été relue et corrigée, elle prend maintenant en compte les modifications apportées avec <em>Swift 2</em>.</p>
</div>

**Contrairement à de nombreux langages, Swift n'a pas besoin qu'on lui indique la fin d'une action dans le code par un point virgule, néanmoins vous pouvez le rajouter si cela vous fait plaisir !**

Les points virgules ne sont pas requis pour les lignes simples qui ne comprennent qu'une seule action mais sont indispensables pour séparer plusieurs actions que l'on souhaite mettre sur la même ligne.

{% highlight swift linenos %}
let chat = "félin"; print(chat)
// affiche "félin"
{% endhighlight swift %}

Par soucis de lisibilité il est plus judicieux d'écrire un code plus aéré en sautant une ligne après chaque action. Ainsi vous évitez de surcharger votre code avec des caractères inutiles et vous vous assurez une lisibilité optimale. C'est également une recommandation à prendre en compte lorsque vous travaillez sur des projets collaboratifs.
