---
layout: post
title:  "Les optionnelles"
date:   2014-06-04 21:33:41
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /optionnelles/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**On utilise les _optionnelles_ dans une situation où une valeur pourrait venir à manquer. On utilise les _optionnelles_ quand :**

<ul><li>Il y a une valeur et elle est égale à <em>x</em> (où <em>x</em> est une inconnue)</li>
<li>Il n'y a pas de valeur du tout</li></ul>

><u>Note :</u> Le concept des optionnelles n'existe pas en C ou en Objective-C. Ce qui s'en rapproche le plus en Objective-C, c'est la possibilité de retourner une valeur <code>nil</code> depuis une méthode qui normalement doit renvoyer un objet, et où <code>nil</code> signifie l'absence d'objet valide. Cependant cela ne marche qu'avec des objets. Pour les autres types, l'Objective-C retourne une valeur spéciale (comme <code>NSNotFound</code>) pour indiquer l'absence de valeur. Cette approche assume que lorsqu'on appelle une méthode, on connait à l'avance ce qu'elle retourne où alors on doit effectuer des tas de tests manuels. Les optionnelles dans *Swift* vous permettent d'indiquer l'absence de valeur dans n'importe quel cas et pour n'importe quel type, sans avoir besoin de constantes spéciales.

Voici un exemple. Le type <code>String</code> de Swift possède une méthode appelée <code>toInt</code>, qui tente de convertir la valeur d'une chaine de caractère en nombre entier de type <code>Int</code>. Néanmoins, toutes les chaines de caractères ne peuvent pas forcement être traduites en nombre entier. La chaine <code>"123"</code> peut être convertie en la valeur numérique <code>123</code>, mais la chaine <code>"hello, world"</code> ne contenant aucun chiffre, ne pourra pas être convertie.

L'exemple ci-dessous utilise la méthode <code>toInt</code> pour tenter la conversion d'une chaine de caractère (<code>String</code>) en entier (<code>Int</code>) :

{% highlight swift linenos %}
let nombreProbable = "123"
let nombreConverti = nombreProbable.toInt()
// la constante nombreProbable sera du type "Int?", ou "optional Int"
{% endhighlight swift %}

Comme la méthode <code>toInt</code> peut échouer, elle retourne un <code>Int</code> optionnel, plutôt qu'un <code>Int</code>. Un <code>Int</code> optionnel sera écrit <code>Int?</code>, et non pas <code>Int</code>. Le point d'interrogation indique que la valeur que contient cette optionnelles peut surrement contenir un <code>Int</code>, mais ce c'est pas une certitude. Elle pourra contenir n'importe quoi d'autre comme une valeur booléenne ou une chaine de caractère. C'est soit un <code>Int</code>, soit rien du tout.

## Identifier le type d'une optionnelle avec *if*

Vous pouvez utiliser les conditions <code>if</code>, pour savoir si une optionnelle contient une valeur. Si une optionnelle possède une valeur, elle est <code>true</code>, si elle n'en a pas, elle est <code>false</code>.

Une fois que vous êtes sûr que l'optionnelle contient une valeur vous pouvez forcer le changement de son type en rajoutant un point d'exclamation à la fin du nom de l'optionnelle. Ce point d'exclamation veut dire *"Je suis sûr que cette optionnelle contient une valeur et je voudrais l'utiliser"*. Cela permet en quelque sorte de convertir le type de l'optionnelle en type définitif :

{% highlight swift linenos %}
if nombreConverti {
    println("\(nombrePossible) est un entier pour \(nombreConverti!)")
} else {
    println("La valeur \(nombrePossible) ne peut pas être convertie")
}
// Affiche "123 est un entier pour 123"
{% endhighlight swift %}

Pour plus d'informations sur les conditions avec <code>if</code>, reportez-vous à la partie *"Flux de control"*.

><u>Note :</u> Essayer d'utiliser le point d'exclamation pour accéder à une valeur optionnelle non-existante causera une erreur de lecture. Assurez-vous que la valeur contient systématiquement autre chose qu'une valeur <code>nil</code> avant d'utiliser le point d'exclamation pour forcer le type d'une valeur.

## Les liaisons optionnelles

On utilise les liaisons optionnelles pour découvrir si une optionnelle contient une valeur, et si c'est le cas, pour rendre cette valeur disponible à travers une constante ou une variable. Les liaisons optionnelles peuvent être utilisées avec les conditions <code>if</code> et <code>while</code> afin de vérifier la présence de valeur à l'intérieur d'une optionnelle, et pour extraire son contenu vers une variable ou une constante en une seule action.

Pour écrire une liaison optionnelle, procédez comme ceci (en utilisant <code>if</code>) :

{% highlight swift linenos %}
if let nomConstante = uneOptionnelle {
    actions
}
{% endhighlight swift %}

Réutilisons l'exemple ci-dessus mais cette fois-ci en utilisant les liaisons optionnelles pour forcer le type d'une optionnelle :

{% highlight swift linenos %}
if let nombreActuel = nombrePossible.toInt() {
    println("\(nombrePossible) est un entier pour \(nombreActuel!)")
} else {
    println("La valeur \(nombrePossible) ne peut pas être convertie")
}
// Affiche "123 est un entier pour 123"
{% endhighlight swift %}

Ce qui peut être lu : *"Si l'entier optionnel retourné par <code>nombrePossible.toInt</code> contient une valeur, créer une nouvelle constante appelée <code>nombreActuel</code> et contenant sa valeur."*

Si la conversion se passe bien, la constante <code>nombreActuel</code> deviendra disponible pour être utilisée dans la première branche de la condition <code>if</code>. Elle a déjà été initialisée avec la valeur contenu dans l'optionnelle, et donc il n'y a plus besoin d'ajouter de point d'exclamation pour accéder à la valeur. Dans cette exemple, <code>nombreActuel</code> est simplement utilisé pour afficher le résultat de la conversion.

Vous pouvez utiliser aussi bien les constantes que les variables avec les liaisons optionnelles. Si vous cherchez ensuite à manipuler la valeur de <code>nombreActuel</code> dans la première branche de la condition <code>if</code>, vous pouvez utiliser une variable plutôt qu'une constante. Souvenez-vous, <a href="http://www.swiftcode.fr/les-constantes-les-variables/" title="Les constantes et les variables">la valeur des constantes ne peut pas être modifiée</a> une fois définie.

## nil

Vous pouvez créer une variable optionnelle en lui assignant la valeur spéciale <code>nil</code> :

{% highlight swift linenos %}
var codeReponseServeur: Int? = 404
// codeReponseServeur contient la valeur 404 de type Int
codeReponseServeur = nil
// codeReponseServeur ne contient maintenant plus de valeur
{% endhighlight swift %}

><u>Note :</u> <code>nil</code> ne peut pas être utilisé si les variables ou les constantes ne sont sont pas des optionnelles. Si une constante ou une variable dans votre code requiert l'absence de valeur, vous devez toujours la déclarer comme optionnelle et du type approprié.

Si vous définissiez une contante ou une variable optionnelle sans lui donner de valeur par défaut, votre constante ou votre variable se verra automatiquement attribuer la valeur <code>nil</code> :

{% highlight swift linenos %}
var reponseSondage: String?
// reponseSondage vaut automatiquement nil
{% endhighlight swift %}

><u>Note :</u> Le <code>nil</code> de Swift n'est pas le même que le <code>nil</code> d'Objective-C. En Objective-C, <code>nil</code> est un pointeur pour les objets non-existants. Dans Swift, <code>nil</code> c'est pas un pointeur, c'est l'absence de valeurs pour un certain type. Les optionnelles de tous les types peuvent être déclaré avec la valeur <code>nil</code>, pas juste les types d'objets.

## Optionnelles implicites

Comme décrit plus haut, les optionnelles permettent à des constantes et des variables d'exister sans avoir de valeur. On peut vérifier si une optionnelle contient une valeur avec la condition <code>if</code>, et grâce à ces conditions il est possible de dévoiler leur contenus en utilisant les liaisons optionnelles.

Parfois, il est clair que depuis la structure du programme, une optionnelle aura forcement une valeur après avoir été définie. Dans ce cas, il est utile de supprimer la possibilité de vérifier si l'optionnelle contient ou non une valeur à chaque fois qu'on souhaite y accéder, parce-qu'on peut confirmer l'existante d'une valeur à chaque fois.

Ces types d'optionnelles sont dites implicites. Une optionnelle implicite se déclare grâce au point d'exclamation en remplacement du point d'interrogation à la fin de son type.

Les optionnelles implicites sont utilisées quand l'existence de la valeur d'une optionnelle est confirmée immédiatement après avoir été définie. Dès lors on assume que son type et sa valeur existeront jusqu'à la fin de l'exécution d'un programme. L'utilisation principale des optionnelles implicites dans Swift est fait lors de l'initialisation des *classes*, comme expliqué dans la partie *"Références inconnues et propriétés des optionnelles implicites"*.

Une optionnelle implicite ressemble en tout point à une optionnelle classique, sauf qu'elle peut être utilisé en tant que valeur non-optionnelle, sans avoir besoin de dévoiler son contenu à chaque fois qu'on y accède. L'exemple suivant montre la différence entre une chaine de caractères optionnelle et une chaine de caractère implicitement non-optionnelle :

{% highlight swift linenos %}
let chaineProbable: String? = "Une chaine optionnelle."
println(chaineProbable!) // Requiert un point d'exclamation
// Affiche "Une chaine optionnelle."
{% endhighlight swift %}

{% highlight swift linenos %}
let chaineCertitude: String! = "C'est une chaine de caractères."
println(chaineCertitude) // Pas besoin de point d'exclamation
// Affiche "C'est une chaine de caractères."
{% endhighlight swift %}

Une fois que votre optionnelle est déclarée come implicite, vous pouvez l'utiliser comme une non-optionnelle automatiquement. Plutôt que de placer un point d'exclamation à chaque fois que vous souhaitez utiliser le nom de votre optionnelle, pensez à la déclarer directement avec ce point d'exclamation si vous êtes sur de ce que vous faite.

><u>Note :</u> Si vous essayez d'accéder à une optionnelle déclarée implicite mais ne possédant aucune valeur, le programme ne fonctionnera pas. Le résultat sera exactement le même en plaçant un point d'exclamation derrière une optionnelle sans valeur.

Vous pouvez toujours traiter les optionnelles implicites comme des optionnelles classiques et vérifier si elle contiennent une valeur :

{% highlight swift linenos %}
if chaineCertitude {
    println(chaineCertitude)
}
// Affiche "C'est une chaine de caractères."
{% endhighlight swift %}

Vous pouvez aussi utiliser les optionnelles implicites avec les liaisons optionnelles pour vérifier leur valeur en une seule action :

{% highlight swift linenos %}
if let chaineDefinitive = chaineCertitude {
    println(chaineDefinitive)
}
// Affiche "C'est une chaine de caractères."
{% endhighlight swift %}

><u>Note :</u> Les optionnelles implicites ne devrait pas être utilisées lorsqu'il y a la possibilité qu'une variable prenne la valeur <code>nil</code> plus tard dans le programme. Utilisez toujours les types optionnels si vous pensez qu'une variable prendra à une moment la valeur <code>nil</code>.