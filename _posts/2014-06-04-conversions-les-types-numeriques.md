---
layout: post
title:  "Conversions entre types"
date:   2014-06-04 21:50:42
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /conversions-les-types-numeriques/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Utilisez au maximum le type <code>Int</code> pour tous les nombres entiers de vos constantes et vos variables dans votre code, même si vous êtes certain qu'il ne seront jamais négatif. Utilisez le type par défaut des entiers dans chaque situation où vos constantes et vos variables sont immédiatement opérationnelles avec votre code et que le compileur peut interpréter leurs types, même pour les valeurs littérales.**

Utilisez un autre type d'entier uniquement quand vous en avez expressément besoin pour réaliser une tâche particulière. Parce-qu'il s'agit d'un typage imposé par une source extérieure ou un autre langage, pour la performance, l'utilisation de la mémoire ou d'autres optimisations nécessaires. Utiliser les types explicites dans ces situations évite d'voir des types de valeurs accidentelles qui ne pourront pas fonctionner avec le reste de votre code.

## Conversions d'entiers

Le nombre total de chiffres qui peuvent être stocké dans un entier constant ou variable est différent en fonction du type numérique. Une constante ou un variable du type <code>Int8</code> peut stocker des nombres entre <code>-128</code> et <code>127</code> alors qu'une constante ou une variable du type <code>UInt8</code> pourra stocker des nombres entre <code>0</code> et <code>255</code>. Un nombre qui ne sera pas amené à rentrer dans cette fourchette autorisé par le typage numérique des valeurs provoquera une erreur lors de la compilation :

{% highlight swift linenos %}
let nonNegatif: UInt = -1 
// UInt8 ne peut pas stocker de nombre négatif
let tropGros: Int8 = Int8.max + 1 
// UInt8 ne peut pas stocker de nombre plus grand que sa valeur maximale
{% endhighlight swift %}

Parce-que chaque type numérique peut stocker une quantité différente de valeurs, vous devrez parfois optez pour une conversion du type numérique au cas par cas. Cette approche vous aidera à convertir de façon claire et explicite vos valeurs et ainsi éviter certaines erreurs dans votre code.

Pour convertir un type spécifique de nombre vers un autre, vous devez initialiser un nouveau nombre du type désiré avec la valeur existante. Dans l'exemple suivant, la constante <code>deuxMille</code> est du type <code>UInt16</code> et l'autre constante <code>un</code> est du type <code>Uint8</code>. Elles ne peuvent pas être additionnée ensemble directement parce-qu'elle ne possèdent pas le même type numérique. Du coup, cet exemple appelle <code>Uint16(un)</code> pour créer un nouveau entier du type <code>UInt16</code> initialisé avec la valeur de <code>un</code> et utilisant sa valeur à la place de l'original :

{% highlight swift linenos %}
let deuxMille: UInt16 = 2_000
let un: UInt8 = 1
let deuxMilleUn = deuxMille + UInt16(un)
{% endhighlight swift %}

Comme les deux côtés de l'addiction sont maintenant du type <code>UInt16</code>, l'opération est permise. Le résultat en sortie de la constante <code>deuxMilleUn</code> est du type <code>UInt16</code> parce-qu'elle est le résultat d'une addition entre deux valeurs de type <code>UInt16</code>.

Dans Swift, <code>Type(valeurInitiale)</code> est le format par défaut pour initialiser une valeur et la passer dans un autre type. Derrière le rideau, <code>UInt16</code> possède un convertisseur qui accepte les valeurs du type <code>UInt8</code>, et ce convertisseur est utilisé pour créer une nouvelle valeur en <code>UInt16</code> depuis un typage <code>UInt8</code> existant. Vous ne pouvez pas passer n'importe quel type ici, uniquement les types qui sont prévus pour être convertis avec <code>UInt16</code>. Il est possible de passer outre cette limitation en utilisant ou en développant des *extensions*.

## Conversion des entiers et des nombres à virgule

Les conversions entre les entiers et les nombres à virgules sont réalisés très simplement :

{% highlight swift linenos %}
let trois = 3
let zeroPoint = 0.14159
let pi = Double(trois) + zeroPoint
// pi vaudra 3.14159 et son type sera convertit en "Double"
{% endhighlight swift %}

Ici, la valeur de la constante <code>trois</code> est utilisée pour créer une nouvelle valeur du type <code>Double</code>, du coup l'addition est possible avec deux parties du même type. Sans cette conversion, l'opération n'aurait pas été permise.

Il est également possible de faire l'inverse et de transformer le nombre à virgule en entier à condition de lui fournir une valeur du type <code>Double</code> ou <code>Float</code> :

{% highlight swift linenos %}
let entierPi = Int(pi)
// entierPi sera alors égal à 3 et du type Int
{% endhighlight swift %}

Les nombres à virgules sont toujours tronqués lorsqu'on les convertis de cette façon en créant un nouvel entier. Ce qui veut dire que <code>4.75</code> devient <code>4</code>, et <code>-3.9</code> devient <code>-3</code>.

><u>Note :</u> Les règles pour combiner une constante ou une variable numérique sont différentes des règles concernant les constantes et les variables littérales. La valeur littérale <code>3</code> peut directement être ajoutée à la valeur littérale <code>0.14159</code>, parce-que les nombres littéraux n'ont pas de type explicite. Leur type est déterminé uniquement lors de la compilation.