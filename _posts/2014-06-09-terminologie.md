---
layout: post
title:  "Terminologie"
date:   2014-06-09 23:48:41
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /terminologie/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Les opérateurs sont unaires, binaires ou ternaires :**

<ul><li>Les opérateurs <em>unaires</em> interviennent sur une cible seule (comme dans <code>-a</code>). Les opérateurs unaires apparaissent immédiatement avant la cible (comme dans <code>!b</code>), et immédiatement après leur cible (comme dans <code>i++</code>).</li>
<li>Les opérateurs <em>binaires</em> interviennent sur deux cibles (comme dans <code>2 + 3</code>) et apparaissent entre ces deux cibles.</li>
<li>Les opérateurs <em>ternaires</em> interviennent sur trois cibles. Comme en C, Swift n'a qu'un seul opérateur ternaire, l'opérateur ternaire de condition (<code>a ? b : c</code>).</li></ul>

Les valeurs que ces opérateurs affectent sont des opérandes. Dans l'expression <code>1 + 2</code>, le symbole <code>+</code> est un opérateur binaire et les deux opérandes sont les valeurs <code>1</code> et <code>2</code>.
