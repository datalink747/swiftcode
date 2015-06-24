---
layout: post
title:  "Compter les caractères"
date:   2015-06-24 16:01:54
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /compter-caracteres/
---

<div class="swift3">
	<p>Vous êtes dans un nouveau chapitre. Traduit directement depuis la dernière version en date de la documentation officielle de <em>Swift 2</em>.</p>
</div>

**Pour récupérer le nombre de caractères dans une chaîne, utilisez la propriété `count` de la prioriété `characters` de la chaîne.**

{% highlight swift linenos %}
let messageBizzare = "Koala 🐨, Escargot 🐌, Pingouin 🐧, Dromadaire 🐪"
print("messageBizzare possède \(messageBizzare.characters.count) caractères")
// messageBizzare possède 40 caractères
{% endhighlight swift linenos %}

Notez que l'utilisation dans *Swift*, d'un combiné Unicode en tant que valeur d'un caractère, n'affecte en rien le score renvoyé par la propriété `count`, il sera toujours à `1`.

Par exemple, si vous initialisez une nouvelle chaîne avec le mot à 4 caractères `cafe`, et que vous le combinez avec l'`ACCENT AÏGU` (`U+0301`) à la fin de la chaîne, le résultat de la propriété `count`, sera toujours de `4`, mais avec 4 caractères dont un `é` et plus un `e` :

{% highlight swift linenos %}
var mot = "cafe"
print("Le nombre de caractères dans \(mot) est de \(mot.characters.count)")
// Le nombre de caractères dans cafe est de 4

word += "\u{301}" // On rajoute l'accent combiné U+0301

print("Le nombre de caractères dans \(mot) est de \(mot.characters.count)")
// Le nombre de caractères dans café est de 4
{% endhighlight swift linenos %}

>**Note :** Les combinés Unicode peuvent être composé d'un ou plusieurs scalaire Unicode. Ce qui signifie que différents caractères, et ses différentes représentations, peuvent avoir besoin d'une quantité différente de mémoire pour être stockés. C'est pour cela que les caractères dans Swift n'occupent pas chacun la même place en mémoire en fonction de leur représentation.












<div class="encours"><p>Cette section est en cours de traduction, merci de revenir plus tard...</p></div>
