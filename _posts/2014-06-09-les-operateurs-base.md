---
layout: post
title:  "Introduction aux opérateurs de base"
date:   2014-06-09 23:47:41
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /les-operateurs-base/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Un opérateur est un symbole spécial ou une phrase qui vous permet de vérifier, changer ou combiner des valeurs. Par exemple, le signe <code>+</code> est un opérateur d'addition qui permet d'ajouter deux nombres ensemble (comme dans <code>let i = 1 + 2</code>). Il est également possible d'utiliser des opérateurs plus complexes, comme par exemple l'opérateur logique _ET_ que l'on écrit <code>&&</code> (comme dans <code>if codePorte && scanRetine</code>) ou l'opérateur d'incrémentation <code>++i</code>, qui est un raccourci pour ajouter la valeur <code>1</code> à <code>i</code>.**

Swift supporte la plupart des opérateurs standards du *langage C* en améliorant certaines capacités pour les rendre plus pratique et éliminer certaines erreurs récurrentes de codage. L'opérateur d'assignement <code>=</code> ne retourne aucune valeur, pour éviter qu'il soit utilisé par erreur lorsque l'opérateur d'égalité <code>==</code> est attendu. Les opérateurs arithmétiques (<code>+</code>, <code>-</code>, <code>*</code>, <code>/</code>, <code>%</code> et beaucoup d'autres) détectent et empêchent les débordements de valeurs, pour prévenir de tout résultat inattendu lorsque l'on travaille avec des nombres qui deviennent plus grands ou plus petits que ce qu'autorise leurs types respectifs. Vous pouvez travaillez avec les débordements de valeurs en utilisant les opérateurs de débordement, décrit dans la partie *Opérateurs de débordement*.

Contrairement au *langage C*, Swift permet de calculer le reste (%) d'une division entre nombres à virgule. Swift propose aussi deux opérateurs de plage (<code>a..b</code> et <code>a...b</code>), dont le C ne dispose pas pour exprimer un raccourci entre une plage de valeurs.

Ce cours décrit les opérateurs communs du langage Swift. Les opérateurs avancés, présentés dans la partie *Opérateurs avancés*, vous permettent de définir vos propres opérateurs personnalisés et d'implémenter les opérateurs standards pour vos propres types personnalisés.