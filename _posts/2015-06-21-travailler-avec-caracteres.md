---
layout: post
title:  "Travailler avec les caractères"
date:   2015-06-21 15:01:54
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /travailler-avec-caracteres/
---

<div class="swift3">
	<p>Vous êtes dans un nouveau chapitre. Traduit directement depuis la dernière version en date de la documentation officielle de <em>Swift 2</em>.</p>
</div>

**Vous pouvez accéder individuellement à chaque caractère d'une chaîne de type `String` grâce à la boucle `for-in`.**

{% highlight swift linenos %}
for caractere in "Lune!🌙".characters {
  print(caractere)
}
// L
// u
// n
// e
// !
// 🌙
{% endhighlight swift linenos %}

Alternativement, vous pouvez créer une constante ou une variable du type `Character` en l'initialisant exactement comme une chaîne de type `String`, mais en lui attributant le type `Character` :

{% highlight swift %}
let pointExclamation: Character = "!"
{% endhighlight swift %}

Les chaînes de caractères peuvent être construite en leur fournissant un tableau de valeurs de type `Character` lors de leur initialisation :

{% highlight swift %}
let luneCaracteres: [Character] = ["L", "u", "n", "e", "!", "🌙"]
let luneChaine = String(luneCaracteres)
print(luneChaine)
// Affiche dans la console "Lune!🌙"
{% endhighlight swift %}
