---
layout: post
title:  "Modifier les collections"
date:   2015-06-24 17:17:54
categories: ['Les collections']
author: Guillaume L.
comments: True
permalink: /modification-collections-swift/
---

<div class="swift3">
	<p>Vous êtes dans un nouveau chapitre. Traduit directement depuis la dernière version en date de la documentation officielle de <em>Swift 2</em>.</p>
</div>

**Si vous créez un tableau, un ensemble ou un dictionnaire, et les assignez à une variable, le type de la collection créé sera modifiable.**

Ce qui signifie que vous pourrez changer la collection après sa création. Vous pourrez ajouter, supprimer ou changer les élements dans la collection.

Si vous assignez un tableau, un ensemble ou un dictionnaire à une contante, la collection ne sera pas modifiable. Sa taille et son contenu ne pourront pas être changés.

>**Note :** C'est une bonne pratique de créer des collections non-modifiables dès lors que vous savez que leurs valeurs n'auront pas besoin d'être changées plus tard. Cela permet au compileur de Swift d'optimiser les performances au chargement de la collection.
