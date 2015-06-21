---
layout: post
title:  "Les chaînes sont des types de valeurs"
date:   2015-06-21 23:54:54
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /chaines-types-valeurs/
---

<div class="swift2">
	<p>Cette section a été relue et corrigée, elle prend maintenant en compte les modifications apportées avec <em>Swift 2</em>.</p>
</div>

**Le type <code>String</code> dans Swift est un type de valeur. Si vous créez une nouvelle valeur <code>String</code>, cette valeur est copiée quand elle est passée à une fonction ou une méthode, ou quand elle est assignée à une constante ou une variable. Dans chaque cas, une nouvelle copie de la valeur est créée, et la nouvelle copie est passée ou assignée, mais pas la version originale. Les types de valeurs sont décrites dans *Structure et Enumérateur, types de valeurs*.**

>**Note :** Ce comportement diffère de celui de <code>NSString</code> dans Cocoa. Quand vous créez une instance <code>NSString</code> dans Cocoa, et la passez dans une fonction, une méthode ou une variable, vous assignez toujours une référence au même <code>NSString</code>. Aucune copie de la chaîne ne prend sa place, à moins que vous ne l'ayez spécifiquement demandé.

Dans *Swift*, le comportement des chaînes de caractères est toujours strictement respecté. Lorsque vous envoyez une valeur de type `String` à une fonction ou une méthode, c'est strictement la valeur que vous avez entré qui est utilisée et jamais autre chose.

Certains langages modifient légèrement les chaînes pour les adapter aux spécificités du langages, ce qui peut parfois provoquer certains comportements inattendu.

Le compileur *Swift* optimise l'utilisation des chaînes, et ne prend jamais de ressources supperflues pour leur gestion. Ce qui signifie que vous obtiendrez toujours de bonnes performances lorsque vous travaillerez avec des valeurs de type `String`.
