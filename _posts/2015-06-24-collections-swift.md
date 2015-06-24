---
layout: post
title:  "Introduction aux collections"
date:   2015-06-24 17:01:54
categories: ['Les collections']
author: Guillaume L.
comments: True
permalink: /collections-swift/
---

<div class="swift3">
	<p>Vous êtes dans un nouveau chapitre. Traduit directement depuis la dernière version en date de la documentation officielle de <em>Swift 2</em>.</p>
</div>

**Swift fournit trois types primaires de collections, les tableaux, les ensembles et les dictionnaires, pour stocker des collections de valeurs. Les tableaux sont des collections de valeurs ordonnées. Les ensembles sont des collections de valeurs uniques non-ordonnées. Enfin, les dictionnaires sont des collections non-ordonnées de valeurs associées à leurs clés.**

![Type de collections en Swift](/img/Capture d’écran 2015-06-24 à 17.23.56.jpg)

Les tableaux, les ensembles et les dictionnaires de Swift possèdent chacun un type de valeurs très différents. Ce qui signifie que vous ne pouvez pas insérer une valeur du mauvais type dans une collection par erreur. Cela signifie également que vous pouvez avoir d'avantage confiance aux données que vous récupérez depuis une collection.

>**Note :** Dans Swift, les types des tableaux, des ensembles et des dictionnaires sont implémentés en tant que collections génériques. Plus d'informations dans la partie sur les "génériques".
