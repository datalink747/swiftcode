---
layout: post
title:  "Chaînes, types de valeurs"
date:   2014-06-09 23:54:54
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /chaines-types-valeurs/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Le type <code>String</code> dans Swift est un type de valeur. Si vous créez une nouvelle valeur <code>String</code>, cette valeur est copiée quand elle est passée à une fonction ou une méthode, ou quand elle est assignée à une constante ou une variable. Dans chaque cas, une nouvelle copie de la valeur est créée, et la nouvelle copie est passée ou assignée, mais pas la version originale. Les types de valeurs sont décrites dans *Structure et Enumérateur, types de valeurs*.**

><u>Note :</u> Ce comportement diffère de celui de <code>NSString</code> dans Cocoa. Quand vous créez une instance <code>NSString</code> dans Cocoa, et la passez dans une fonction, une méthode ou une variable, vous assignez toujours une référence au même <code>NSString</code>. Aucune copie de la chaîne ne prend sa place, à moins que vous ne l'ayez spécifiquement demandé.

<div class="encours"><p>Ce chapitre est en cours de traduction, merci de revenir plus tard...</p></div>