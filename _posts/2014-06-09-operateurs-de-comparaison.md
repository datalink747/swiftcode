---
layout: post
title:  "Opérateurs de comparaison"
date:   2014-06-09 23:49:45
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /operateurs-de-comparaison/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Swift supporte tous les opérateurs de comparaison standards que l'on retrouve aussi dans le langage C :**

<ul><li>Égal à (<code>a == b</code>)</li>
<li>Non égal à (<code>a != b</code>)</li>
<li>Plus grand que (<code>a > b</code>)</li>
<li>Plus petit que (<code>a < b</code>)</li>
<li>Plus grand ou égal à (<code>a >= b</code>)</li>
<li>Plus petit ou égal à (<code>a <= b</code>)</li></ul>

><u>Note :</u> Swift apporte aussi deux opérateurs d'identité (<code>===</code> et <code>!==</code>), qui sont utilisé pour tester les cas où deux références d'objets réfèrent tous les deux à la même instance. Pour plus d'informations, consultez le chapitre *"Classes et structures"*.

Chaque opérateur de comparaison retourne une valeur booléenne pour indiquer si la comparaison est vraie ou fausse :

{% highlight swift linenos %}
1 == 1    // "true", 1 est égal à 1
2 != 1    // "true", 2 n'est pas égal à 1
2 > 1     // "true", 2 est plus grand que 1
1 < 2     // "true", 1 est plus petit que 2
1 >= 1    // "true", 1 est plus grand ou égal à 1
2 <= 1    // "false", 2 n'est pas plus petit ou égal à 1
{% endhighlight swift linenos %}

Les opérateurs de comparaisons sont aussi utilisés avec les *conditions*, comme par exemple avec <code>if</code> :

{% highlight swift linenos %}
let nom = "world"
if nom == "world" {
    println("hello, world")
} else {
    println("Désolé \(nom), je ne vous reconnait pas")
}
// Affiche "hello, world", car nom est égal à "world"
{% endhighlight swift linenos %}