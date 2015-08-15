---
layout: post
title:  "Introduction à Swift"
date:   2015-06-20 12:58:51
categories: ['Les bases']
author: Guillaume L.
comments: True
permalink: /introduction-swift/
---

<div class="swift2">
	<p>Cette section a été relue et corrigée, elle prend maintenant en compte les modifications apportées avec <em>Swift 2</em>.</p>
</div>

**Swift est un nouveau langage de programmation pour le développement d’application iOS, watchOS et Mac OS X. Néanmoins, certaines parties du langage Swift seront familière si vous avez déjà une expérience dans le développement C et Objective-C.**

Swift fournit ses propres versions des types fondamentaux du C et de l’Objective-C, incluant `Int` pour les entiers, `Double` and `Float` pour les nombres à virgule flottante, `Bool` pour les valeurs booléennes et `String` pour les données textuelles. Swift fournit aussi une version puissante des deux principaux types de collection, `Array` et `Dictionary` pour les tableaux et les dictionnaires.

Comme le C, Swift utilise les variables pour stocker et se référer aux valeurs identifiées par leur nom. Swift permet aussi l’utilisation des variables dont les valeurs ne peuvent pas être changées. Aussi appelées constantes, elles sont plus puissantes que dans le langage C. Les constantes sont utilisées partout avec Swift pour obtenir un code clair et sans faille de sécurité dans la mesure où vous travaillez avec des valeurs qui n’ont pas besoin d’être modifiées.

En supplément des types familiers, Swift introduit d’autres types avancés que ne possède pas l’Objective-C. Il s’agit notamment de tuples (listes non-mutables), qui vous permettent de créer et de passer par des regroupements de valeurs. Les Tuples peuvent retourner de multiples valeurs depuis une fonction comme une valeur unique composée.

Swift introduit aussi les types optionnels, qui acceptent l’absence de valeur. Les types optionnels fonctionnent de la façon suivante : *« Il y a une valeur et elle est égale à x (ou x est une inconnue) »* ou *« Il n’y a pas de valeur du tout »*. Utiliser un type optionnel revient à utiliser `nil` avec des pointeurs en Objective-C, mais cette fois ils marchent avec n’importe quel type, pas juste les classes. Ils sont plus sécurisés et plus expressifs que les pointeurs `nil` en Objective-C et sont le coeur de nombreuses fonctionnalités plus puissantes les unes que les autres du langage Swift.

Les types optionnels sont un exemple qui définit Swift comme un langage aux *types sécurisés*. Swift vous aide à être clair dans le typage des valeurs qui sont attendues pour un code fonctionnel. Si une partie de votre code attend une chaine de caractère (*String*), le typage sécurisé vous prévient si par erreur vous avez typé votre variable comme un *Int*. Cela permet de déceler et de réparer les erreurs très rapidement dans votre processus de développement.
