---
layout: post
title:  "Les nombres à virgule flottante"
date:   2014-06-05 8:00:40
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /les-nombres-virgule-flottante/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Les nombres à virgule flottante sont des nombres avec une part fractionné comme <code>3.14159</code> ou <code>-273.15</code>. La virgule est en en fait un point puisqu'on utilise ici la nomenclature anglo-saxonne pour séparer les décimales de l'entier. On les appelle aussi plus communément les nombres à virgules.**

Les types des nombres à virgules représentent une beaucoup plus large palette de valeurs possibles par rapport aux types des entiers, et peuvent stocker des nombres beaucoup plus longs mais surtout beaucoup plus petits que ce que peut faire le type <code>Int</code>. Swift propose deux types de nombres à virgules dont le signe est connu :

<ul><li>Le type <code>Double</code> représente un nombre à virgule en 64 bits. Utilisez-le quand votre nombre à virgule doit être très grand ou particulièrement précis.</li>
<li>Le type <code>Float</code> représente un nombre à virgule en 32 bits. Utilisez-le quand votre nombre à virgule ne requiert pas la précision d'un nombre en 64 bits.</li></ul>

><u>Note :</u> Le type <code>Double</code> possède une précision pouvant aller jusqu'à 15 décimales alors que le type <code>Float</code> n'accepte que 6 chiffres après la virgule. le type de vos nombres à virgule dépend de vos besoins, de la plateforme sur laquelle vous travaillez et de votre code.