---
layout: post
title:  "Introduction aux chaînes de caractères"
date:   2014-06-09 23:50:49
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /les-chaines-les-caracteres/
---

**Une chaîne est une suite ordonnée de caractères, tel que _"Hello, world"_ ou _"Albatros"_. Les chaînes dans Swift sont représentées par le type <code>String</code> (chaîne), qui à son tour représente une collection de valeurs du type <code>Character</code>.**

Les _chaînes de caractères_ fournissent un moyen rapide de travailler avec du texte brut dans votre code. La syntaxe pour la création et la manipulation des chaînes avec Swift est similaire à la syntaxe en langage C. Les chaînes de caractères peuvent être facilement concaténées les unes à la suite des autres grâce au symbole <code>+</code> et stockée dans une variable ou une constante comme n'importe quelle autre valeur en Swift.

En plus de la simplicité de sa syntaxe, l’implémentation des chaines en Swift est moderne et rapide. Chaque chaîne est composée de plusieurs caractères Unicode indépendants, et fournit le moyen accéder à ces caractères un par un de différente façon.

Les chaînes peuvent aussi être utilisées avec les constantes, les variables, les littéraux, et d'autres expressions via un procédé d'interpolation. Ceci rend plus facile la création de valeurs personnalisées pour l'affichage, le stockage, et l’impression.

><u>Note :</u> Le type <code>String</code> en Swift ressemble beaucoup à la classe <code>NSString</code> de *Foundation*. Si vous travaillez avec le framework *Foundation* pour Cocoa et Cocoa Touch, l'API complète <code>NSString</code> est accessible lorsque vous appelez ou créez une valeur de type <code>String</code>. Vous pouvez aussi utiliser une valeur <code>String</code> avec n'importe quelle API qui requiert une instance <code>NSString</code>.