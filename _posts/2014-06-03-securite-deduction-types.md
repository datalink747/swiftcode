---
layout: post
title:  "Sécurité et déduction des types"
date:   2014-06-03 7:03:42
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /securite-deduction-types/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Swift est un langage aux types sécurisés. Ce qui signifie qu'il vous encourage a être clair sur les types des valeurs qui doivent intervenir dans votre code. Si un bout de votre code attend une chaîne de caractères (<code>String</code>), vous ne pourrez pas passer avec un nombre entier (<code>Int</code>) par mégarde.**

Parce-que Swift est un langage au type sécurisé, il vérifie tous les types lorsqu'il compile votre code et vous indique les problèmes de types comme étant des erreurs. Cela vous permet de corriger le problème rapidement et le plus tôt possible dans votre processus de développement.

La vérification des types vous aide à éviter les erreurs lorsque vous travaillez sur différents types de valeurs. Cependant, cela ne veut pas dire que vous devez forcement spécifier le type de chaque constante et de chaque variable que vous déclarez. Si vous ne spécifiez pas le type de vos valeurs, Swift est capable de déduire le type approprié. La déduction des types permet au compileur de deviner le type d'une expression particulière automatiquement lorsqu'il compile votre code, simplement en examinant les valeurs que vous avez fourni.

À cause de la déduction des types, Swift requiert beaucoup moins de déclarations de type que des langages comme le C ou l'Objective-C. Les constantes et les variables sont toujours explicitement typées, et il n'est plus nécessaire de passer trop de temps là-dessus maintenant.

La déduction des types est particulièrement utile lorsque vous déclarez une constante ou une variable avec une valeur initiale. Cela fonctionne aussi en assignant une valeur factice au moment de la déclaration. Par exemple si votre variable est prédestinée à être et rester un entier (<code>Int</code>), vous pouvez la déclarer avec un entier factice pour que le compileur déduise simplement son type tout au long de son existence.

{% highlight swift %}
var variableTest = 42 // Le compileur déduit que variableTest est un Int
{% endhighlight %}

De même, si vous ne spécifiez pas le type d'une constante mais que vous lui donnez une valeur avec une virgule, Swift comprendra qu'il s'agit d'un <code>Double</code> :

{% highlight swift %}
let pi = 3.14159 // pi est une constante de type Double
{% endhighlight %}

Swift choisi toujours le type <code>Double</code> pour les nombres à virgule flottante dont le type n'est pas spécifié (plutôt que <code>Float</code>) pour permettre des extensions plus larges.

Si vous combinez une valeur factice comprenant un entier et un nombre à virgule, le type de l'expression sera déduit comme étant un <code>Double</code> en fonction du contexte :

{% highlight swift %}
let autrePi = 3 + 0.141559 // autrePi est un Double
{% endhighlight %}

La valeur <code>3</code> n'a pas de type explicite et comme elle est additionnée avec une valeur comprenant un nombre à virgule, <code>autrePi</code> est automatiquement défini comme un <code>Double</code> après avoir obtenu le résultat de l'addition.