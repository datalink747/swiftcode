---
layout: post
title:  "Booléens et tuples"
date:   2014-06-04 21:34:42
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /tuples-booleens/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Swift possède un type de base, les _Booléens_, appelés <code>Bool</code>. Les valeurs booléennes sont définies comme _logiques_, parce-qu'elles ne peuvent qu'être _vraies_ ou _fausses_. Swift possède deux valeurs booléennes constantes, <code>true</code> et <code>false</code> :**

{% highlight swift linenos %}
let orangeEstOrange = true
let navetEstDelicieux = false
{% endhighlight swift %}

Le type de <code>orangeEstOrange</code> et <code>navetEstDelicieux</code> a été définit comme <code>Bool</code> du fait que les deux contantes ont été initialisées avec un valeur littérale booléenne. Comme pour les <code>Int</code> et les <code>Double</code> que nous avons vu précédemment, vous n'avez pas besoin de déclarer vos variables ou vos constantes en tant que <code>Bool</code> si vous leur attribuez la valeur <code>true</code> ou <code>false</code> lors de leur création. La déduction de type de Swift vous aide à obtenir un code plus concis et lisible lorsque vous initialisez une constante ou une variable avec une valeur dont le type est déjà connu.

Les valeurs booléennes sont particulièrement utiles quand vous travaillez avec des conditions, comme c'est le cas par exemple avec <code>if</code> :

{% highlight swift linenos %}
if navetEstDelicieux {
    println("Mmmh ! Les navets gouteux !")
} else {
    println("Beurk ! Les navets sont horribles !")
}
// Le programme affichera "Beurk ! Les navets sont horribles !"
{% endhighlight swift %}

Les conditions comme le <code>if</code> sont expliquées plus en détails dans la partie *"Flux de contrôle"*.

La sécurisation des types de Swift empêche les valeurs non-booléennes de se substituer au type <code>Bool</code>. L'exemple suivant provoque une erreur à la compilation :

{% highlight swift linenos %}
let i = 1
if i {
    // Cet exemple ne pourra pas être compilé !
}
{% endhighlight swift %}

Cependant l'exemple alternatif ci-dessous est valide :

{% highlight swift linenos %}
let i = 1
if i == 1 {
    // Cet exemple pourra être compilé !
}
{% endhighlight swift %}

Le résultat de <code>i == 1</code> est une comparaison de type <code>Bool</code>, et dans ce second exemple, la vérification des types ne posera pas de problème. Pour plus de détails référez-vous à la partie *"Opérateurs de base"*.

Comme avec les autres exemples sur la sécurisation des types du langage Swift, cette approche permet d'éviter les erreurs accidentelles et assure que vos intentions sont toujours parfaitement retranscrites dans chaque section de votre code.

## Les tuples

Les *Tuples* servent à regrouper de nombreuses valeurs en un seule valeur composée unique. Les valeurs d'un tuple peut être de n'importe quel type et n'ont pas forcement besoin d'être du même type les unes par rapport aux autres.

Dans cet exemple, (<code>404, "Introuvable"</code>) est un tuple décrivant un code d'erreur *HTTP*. Ce code d'erreur *HTTP* est une valeur spéciale retournée par un serveur web lorsque vous souhaitez charger une page. Le code <code>404 Introuvable</code> est retourné si la page web demandée n'existe pas.

{% highlight swift linenos %}
let erreur404Http = (404, "Introuvable")
// le code d'erreur est du type (Int, String) et égale à (404, Introuvable)
{% endhighlight swift %}

Le tuple <code>(404, "Introuvable")</code> regroupe ensemble un entier et une chaine de caractères pour produire un code d'erreur *HTTP* composé de deux valeurs : un nombre pour la machine et une description compréhensible pour l'homme. On dit que le type du tuple est <code>(Int, String)</code>.

Vous pouvez créer des tuples avec n'importe quelle combinaison de types, ils peuvent contenir beaucoup plus de deux valeurs et elles ne doivent pas nécessairement avoir le même type. Rien ne vous empêche cependant d'avoir un tuple du type <code>(Int, Int, Int)</code>, ou <code>(String, Bool)</code>. Toutes les combinaisons sont possibles.

Vous pouvez décomposer le contenu d'un tuple en plusieurs constantes ou variables séparées, auxquelles vous accédez comme d'habitude :

{% highlight swift linenos %}
let (codeErreur, messageErreur) = erreur404Http
println("Le code d'erreur est \(codeErreur)")
// Affiche "Le code d'erreur est 404"
println("Le message d'erreur est \(messageErreur)")
// Affiche "Le message d'erreur est Introuvable"
{% endhighlight swift %}

Si vous avez juste besoin de récupérer une partie des valeurs d'un tuple, vous pouvez ignorer les autres parties en utilisant un *underscore* lors de la décomposition du tuple :

{% highlight swift linenos %}
let (justeCodeErreur, _) = erreur404Http
println("Le code d'erreur est \(justeCodeErreur)")
// Affiche "Le code d'erreur est 404"
{% endhighlight swift %}

De façon alternative, vous pouvez accéder à la valeur d'un élément individuellement en utilisant son index (commençant à zéro) :

{% highlight swift linenos %}
println("Le code d'erreur est \(erreur404Http.0)")
// Affiche "Le code d'erreur est 404"
println("Le message d'erreur est \(erreur404Http.1)")
// Affiche "Le message d'erreur est 404"
{% endhighlight swift %}

Vous pouvez nommer chacun des éléments d'un tuple de façon individuelle lorsque vous initialisez votre constante :

{% highlight swift %}
let erreur200Http = (codeErreur: 200, messageErreur: "OK")
{% endhighlight swift %}

Si vous nommez les éléments d'un tuple, vous pouvez utilisez le nom de ces éléments pour accéder à leur valeur respective :

{% highlight swift linenos %}
println("Le code d'erreur est \(erreur200Http.codeErreur)")
// Affiche "Le code d'erreur est 200"
println("Le message d'erreur est \(erreur200Http.messageErreur)")
// Affiche "Le message d'erreur est OK"
{% endhighlight swift %}

Les tuples sont particulièrement utile pour retourner des valeurs de fonctions. Une fonction qui essaie de récupérer une page web pourrait retourner un tuple du type <code>(Int, String)</code> pour décrire si le chargement de la page a été couronné de succès ou non. En retournant un tuple avec deux valeurs distinctes, chacune d'un type différent, la fonction  reçoit des informations beaucoup plus pertinente qu'elle n'aurait pas forcement pu traiter efficacement s'il avait s'agit uniquement de valeurs du type <code>String</code>. Pour plus d'informations, reportez-vous à la partie *"Fonctions aux multiples valeurs"*.

><u>Note :</u> Les tuples sont utiles pour stocker temporairement un groupe de valeurs. Elles ne sont pas là pour créer une structure de données complexes. Si la structure de vos données requiert un stockage sur la long terme, préférez une structure de vos données architecturées autour des classes, plutôt qu'autour des tuples. Pour plus d'informations, référez-vous à la partie *"Classes et structures"*.