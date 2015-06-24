---
layout: post
title:  "Les tableaux"
date:   2015-06-24 18:22:54
categories: ['Les collections']
author: Guillaume L.
comments: True
permalink: /tableaux-swift/
---

<div class="swift3">
	<p>Vous êtes dans un nouveau chapitre. Traduit directement depuis la dernière version en date de la documentation officielle de <em>Swift 2</em>.</p>
</div>

**Les tableaux stockent des valeurs du même type de façon ordonnées comme dans une liste. La même valeur peut apparaître dans un tableau à plusieurs reprises et à différente position.**

>**Note :** Le type `Array` de Swift, est une amélioration de la classe `NSArray` de Foundation. Pour plus d'information à propos des tableaux dans Foundation et Cocoa, merci de vous reporter à la documentation associée.

## La syntaxe abrégée du type tableau

Le type des tableaux en Swift s'écrit de façon complète `Array<T>`, où `T` est le type des valeurs que le tableau est autorisé à stocker. Vous pouvez écrire le type des valeurs d'un tableau de la façon abrégée suivante : `[T]`. Les deux formes fonctionnent de façon identique, la forme abbrégée est néanmoins préférée et plus utilisée au travers de ce guide et lorsque nous parlerons du type des valeurs contenues dans un tableau.

## Créer un tableau vide

Vous pouvez créer un tableau vide d'un certain type, en utilisant la syntaxe d'initialisation suivante :

{% highlight swift linenos %}
var plusieursEntiers = [Int]()
print("plusieursEntiers est du type [Int] et possède \(plusieursEntiers.count) élements.")
// plusieursEntiers est du type [Int] et possède 0 élements.
{% endhighlight swift linenos %}

Notez que le type de la variable `plusieursEntiers` devient `[Int]` dès l'initialisation.

Par ailleurs, si le contexte fournit les informations sur le type, comme une argument d'une fonction ou une variable ou une constante déjà typées, vous pouvez créer un tableau vide en ne mettant que les crochets `[]` :

{% highlight swift linenos %}
plusieursEntiers.append(3)
// plusieursEntiers contient maintenant une valeur de type Int
plusieursEntiers = []
// plusieursEntiers est maintenant un tableau vide, mais toujours du type [Int]
{% endhighlight swift linenos %}

## Créer un tableau avec une valeur par défaut

## Créer un tableau depuis deux tableaux

## Créer un tableau de chaînes

## Lire et modifier un tableau

## Les itérations avec les tableaux













<div class="encours"><p>Cette section est en cours de traduction, merci de revenir plus tard...</p></div>
