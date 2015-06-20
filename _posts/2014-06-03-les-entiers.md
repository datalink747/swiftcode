---
layout: post
title:  "Les entiers"
date:   2014-06-03 8:21:11
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /les-entiers/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Les entiers sont des nombres non-fractionnés comme <code>42</code> et <code>-23</code>. Les entiers possèdent un signe (positif, zéro ou négatif) ou n'en possèdent pas si ils sont positifs ou égaux à zéro.**

Swift prévoit des entiers avec ou sans signes sous la forme 8, 16, 32 et 64 bits. Ces entiers suivent des conventions de nommage similaires au langage C, un entier sans signe en 8 bits est du type <code>UInt8</code>, et un entier en 32 bits dont le signe est connu est du type <code>Int32</code>. Comme tous les types dans Swift, les types d'entiers commencent par une lettre en majuscule.

## Les limites des entiers

Vous pouvez accéder aux valeurs minimales et maximales de chaque type d'entier avec leurs propriétés <code>min</code> et <code>max</code> :

{% highlight swift linenos %}
let minValue = UInt8.min //minValue vaut 0 et est du type UInt8
let maxValue = UInt8.max //maxValue vaut 255 et est du type UInt8
{% endhighlight swift %}

Les valeurs de ces propriétés sont taillées en fonction du type du nombre entier (<code>UInt8</code> dans l'exemple ci-dessus) et peuvent être utilisées dans des expressions à côté de valeurs du même type.

## Int

Dans la plupart des cas, vous n'aurez pas besoin de spécifier une taille spécifique pour vos entiers à l'intérieur de votre code. Swift propose un type d'entier additionnel, <code>Int</code>, qui possèdent la même taille que le système d'exploitation que vous utilisez :

<ul><li>Sur les plateformes 32 bits, <code>Int</code> possède la même taille que <code>Int32</code>.</li>
<li>Sur les plateformes 64 bits, <code>Int</code> possède la même taille que <code>Int64</code>.</li></ul>

Si vous n'avez pas besoin, de travailler avec une taille spécifique d'entier, utilisez toujours <code>Int</code> pour les valeurs de vos entiers dans votre code. Cela facilite la cohérence et l'interopérabilité. Même si vous travaillez dans un environnement 32 bits, avec <code>Int</code> vous pouvez stocker une valeur entre <code>-2 147 483 648</code> et <code>2 147 483 647</code>, et c'est surement largement assez grand pour la grande majorité des besoins !

## UInt

Swift permet aussi d'avoir des entiers sans signe du type <code>UInt</code>, qui possède la même taille que le système d'exploitation que vous utilisez :

<ul><li>Sur les plateformes 32 bits, <code>UInt</code> possède la même taille que <code>UInt32</code>.</li>
<li>Sur les plateformes 64 bits, <code>UInt</code> possède la même taille que <code>UInt64</code>.</li></ul>

><u>Note :</u> Utilisez <code>UInt</code> uniquement quand vous avez spécialement besoin d'un entier sans signe avec la taille de votre plateforme (32 ou 64 bits). Si ce n'est pas le cas préférez <code>Int</code> même si vous savez que la valeur ne sera jamais négative.