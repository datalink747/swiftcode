---
layout: post
title:  "Opérateurs d'intervalles"
date:   2014-06-09 23:49:48
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /operateurs-intervalles/
---

**Swift inclut deux opérateur d'intervalles, qui sont des raccourcis pour exprimer une fourchette de valeurs.**

## Opérateur d'intervalle fermé

L'opérateur d'intervalle fermé (<code>a...b</code>) définit une intervalle de valeurs entre <code>a</code> et <code>b</code> en incluant également les valeurs de <code>a</code> et de <code>b</code>.

L'opérateur d'intervalle fermé est très utile pour agir sur une plage de valeur sans avoir besoin de toutes les citer. Il est très utilisé dans les boucles de type <code>for-in</code> :

{% highlight swift linenos %}
for index in 1...5 {
    println("\(index) multiplié par 5 vaut \(index * 5)")
}
// 1 multiplié par 5 vaut 5
// 2 multiplié par 5 vaut 10
// 3 multiplié par 5 vaut 15
// 4 multiplié par 5 vaut 20
// 5 multiplié par 5 vaut 25
{% endhighlight swift linenos %}

Pour plus d'information sur les boucles <code>for-in</code>, reportez-vous à la rubrique *"Contrôle de flux"*.

## Opérateur d'intervalle semi-fermé

L'opérateur d'intervalle semi-fermé (<code>a..b</code>) définit une intervalle de valeurs entre <code>a</code> et <code>b</code> démarrant et incluant <code>a</code>, mais n'incluant pas <code>b</code>. Voilà pourquoi on dit qu'il est semi-fermé.

Les intervalles semi-fermées sont particulièrement utiles lorsque vous travaillez avec des tableaux (<code>array</code>), dont la première clé d'index commence à zéro. Dans ce cas précis, vous savez où la liste démarre mais vous ne savez pas où elle se termine :

{% highlight swift linenos %}
let noms = ["Anna", "Alex", "Brian", "Jack"]
let compteur = noms.count
for i in 0..compteur {
    println("La personne n° \(i + 1)  est appelée \(noms[i])")
}
// La personne n°1 est appelée Anna
// La personne n°2 est appelée Alex
// La personne n°3 est appelée Brian
// La personne n°4 est appelée Jack
{% endhighlight swift linenos %}

Notez que le tableau contient 4 objets, mais <code>0..compteur</code> ne compte que jusqu'à 3 (la clé du dernier objet dans le tableau), comme il s'agit d'une intervalle semi-fermée. Pour plus d'informations reportez-vous à la section *"tableaux"*.