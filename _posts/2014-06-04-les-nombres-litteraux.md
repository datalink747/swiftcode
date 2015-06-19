---
layout: post
title:  "Les nombres littéraux"
date:   2014-06-04 21:59:42
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /les-nombres-litteraux/
---

**Une valeur littérale est une valeur qui contient des lettres représentant des chiffres. En général il s'agit d'un code pouvant être interprété différemment en fonction ce que l'on souhaite obtenir.**

Les entiers littéraux peuvent être écrits de différentes manières :

<ul><li>Un nombre <em>décimal</em>, sans aucun préfixe</li>
<li>Un nombre <em>binaire</em>, avec un préfixe <code>0b</code></li>
<li>Un nombre <em>octal</em>, avec un préfixe <code>0o</code></li>
<li>Un nombre <em>hexadécimal</em>, avec un préfixe <code>0x</code></li></ul>

Tous ces entiers littéraux correspondent à la valeur décimale de <code>17</code> :

{% highlight swift linenos %}
let decimalEntier = 17
let binaireEntier = 0b10001 // 17 en binaire
let octalEntier = 0o21 // 17 en octal
let hexadecimalEntier = 0x11 // 17 en hexadécimal
{% endhighlight swift %}

Les nombres à virgule littéraux peuvent être décimaux (sans préfixe), ou hexadécimaux (avec le préfixe <code>0x</code>). Ils doivent juste toujours avoir un nombre décimal (ou hexadécimal) de chaque côté de la virgule. Ils peuvent aussi avoir un exposant optionnel, indiqué avec un <code>e</code> majuscule ou minuscule pour les nombres décimaux et un <code>p</code> majuscule ou minuscule pour les nombres hexadécimaux.

Pour les nombres décimaux avec un exposant, la base du nombre est multipliée par 10<sup>exp</sup> :

<ul><li><code>1.25e2</code> signifie <strong>1.25 x 10²</strong> ou <code>125.0</code></li>
<li><code>1.25e-2</code> signifie <strong>1.25 x 10⁻²</strong> ou <code>0.0125</code></li></ul>

Pour les nombres hexadécimaux avec un exposant, la base du nombre est multipliée par 2<sup>exp</sup> :

<ul><li><code>0xFp2</code> signifie <strong>15 x 2²</strong> ou <code>60.0</code></li>
<li><code>0xFp-2</code> signifie <strong>15 x 2⁻²</strong> ou <code>3.75</code></li></ul>

Tous les nombres à virgule ci-dessous ont une valeur décimale de <code>12.1875</code> :

{% highlight swift linenos %}
let decimalDouble = 12.1875
let exposantDouble = 1.21875e1
let hexadecimalDouble = 0xC.3p0
{% endhighlight swift %}

Les nombres littéraux peuvent contenir un formatage supplémentaire afin de les rendre plus lisibles. Entiers comme nombres à virgule, peuvent être *rembourrés* avec des zéros supplémentaires et des underscores pour aider à la lecture. En aucun cas, le formatage n'affecte la valeur du nombre littéral :

{% highlight swift linenos %}
let decimalDouble = 000123.456
let unMillion = 1_000_000
let plusdunMillion = 1_000_000.000_000_1
{% endhighlight swift %}

N'oubliez pas cette astuce, elle peut s'avérer très pratique lorsque vous serez amené à manipuler des nombres très très grands. Bien sur la technique des puissances et des exposants est une bonne manière de réduire le nombre de caractères de votre code et d'utiliser la puissance des machines qui exécuteront votre code, mais au moins vous êtes au courant !