---
layout: post
title:  "Les opérateurs logiques"
date:   2014-06-09 23:49:49
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /operateurs-logiques/
---

**Les opérateurs logiques modifient ou combinent deux valeurs booléennes logiques <code>true</code> et <code>false</code>. Swift supporte les trois opérateurs logiques standards que l'on retrouve dans les langages basés sur le C :**

<ul><li>L'opérateur logique <strong>NOT</strong> (<code>!a</code>)</li>
<li>L'opérateur logique <strong>AND</strong> (<code>a && b</code>)</li>
<li>L'opérateur logique <strong>OR</strong> (<code>a || b</code>)</li></ul>

## Opérateur logique *NOT*

L'opérateur logique *NOT* (<code>!a</code>) inverse la valeur d'un booléen, <code>true</code> devient <code>false</code> et <code>false</code> devient <code>true</code>.

L'opérateur logique *NOT* est toujours un préfixe, il apparait immédiatement avant la valeur sur laquelle il opère, sans ajouter d'espace. Il peut être lu de la façon suivante : *"n'est pas <code>a</code>"*, comme vous pouvez le voir dans l'exemple ci-dessous :

{% highlight swift linenos %}
let entreeAutorise = false
if !entreeAutorise {
    println("ACCÈS REFUSÉ")
}
// Affiche "ACCÈS REFUSÉ"
{% endhighlight swift linenos %}

La phrase <code>if !entreeAutorise</code> peut être lue *"Si l'entrée n'est pas autorisé"*. La ligne suivante est exécutée uniquement si l'entrée non autorisée est <code>true</code>. Dans cet exemple choisissez bien le nom de vos variables et de vos constantes booléennes, pour obtenir un code plus lisible et compréhensible, pour prévenir les doubles négatives ou les confusions.

## Opérateur logique *AND*

L'opérateur logique *AND* (<code>a && b</code>) crée une expression logique ou les deux valeurs doivent être <code>true</code> pour que l'ensemble de l'expression soit aussi <code>true</code>. Si l'une des deux valeurs est <code>false</code>, l'expression devient aussi <code>false</code>. En réalité, si la première valeur est <code>false</code>, la seconde valeur n'est même pas évaluée, car il est impossible qu'au final l'expression puisse être <code>true</code>.

Cet exemple initialise deux constantes booléennes et n'autorise l'accès que si elles sont toutes les deux à <code>true</code> :

{% highlight swift linenos %}
let codePorte = true
let scanRetinien = false
if codePorte && scanRetinien {
    println("Welcome !")
} else {
    println("ACCÈS REFUSÉ")
}// Affiche "ACCÈS REFUSÉ"
{% endhighlight swift linenos %}

## Opérateur logique *OR*

L'opérateur logique *OR* (<code>a || b</code>) se place toujours entre deux valeurs et correspond à barres parallèles adjacentes. Ce caractère est facile à trouver sur un clavier *Windows*, pour *Mac* il faudra presser les touches <kbd>ALT</kbd> + <kbd>SHIFT</kbd> + <kbd>L</kbd>.

L'opérateur logique *OR* permet de créer une expression logique où l'une ou toutes les valeurs de l'expression valent <code>true</code>. Si c'est le cas alors l'expression complète vaut elle aussi <code>true</code>.

Comme pour l'opérateur logique *AND* vu ci-dessus, l'opérateur logique *OR* n'analysera pas les autres valeurs de l'expression si la première est déjà à <code>true</code>. Il est évident que du coup toute l'expression sera forcement à <code>true</code>.

Dans l'exemple ci-dessous, le premier booléen est <code>false</code> mais la seconde valeur est <code>true</code>. L'expression complète est évaluée à <code>true</code> et l'accès est autorisé :

{% highlight swift linenos %}
let clePorte = false
let reinitialisationCode = true
if clePorte || reinitialisationCode {
    println("Welcome !")
} else {
    println("ACCÈS REFUSÉ")
}// Affiche "Welcome !"
{% endhighlight swift linenos %}

## Combiner les opérateurs logiques

Vous pouvez combiner de nombreux opérateurs logiques pour créer de plus longues expressions à faire vérifier par votre code :

{% highlight swift linenos %}
if codePorte && scanRetinien || clePorte || reinitialisationCode {
    println("Welcome !")
} else {
    println("ACCÈS REFUSÉ")
}// Affiche "Welcome !"
{% endhighlight swift linenos %}

Cet exemple utilise de nombreux opérateurs logiques comme <code>&&</code> et <code>||</code> pour créer une expression plus longue. Cependant, les opérateurs <code>&&</code> et <code>||</code> n'opèrent chacun uniquement que sur deux valeurs, du coup il s'agit ici en fait de trois plus petites expressions collées les unes aux autres.

L'expression peut être lue : *"Si j'ai entré correctement le code de la porte et passé avec succès le scan rétinien; ou si j'ai la clé de la porte; ou je sais réinitialiser le code, alors je suis autorisé à entrer"*.

En se basant sur les valeurs des constantes que nous avons initié dans nos exemples, la première expression est <code>false</code>. Cependant je sais réinitialiser le code d'entrée, du coup l'expression complète est <code>true</code>. La suite de l'expression n'a pas besoin d'être analysée puisqu'elle sera forcement <code>true</code>.

## En ajoutant des parenthèses

Si le cours des opérations de vérifications effectuées par les opérateurs logiques ne vous convient pas, vous pouvez ajouter des parenthèses pour séparer les expressions de l'expressions globale comme bon vous semble. Même si vos parenthèses ne modifient pas la façon dont est interprétée l'expression globale, elles peuvent faciliter la lecture de votre code. Dans l'exemple des portes de de leur code d'accès, il peut être utile d'ajouter des parenthèses pour faciliter la compréhension de l'expression globale :

{% highlight swift linenos %}
if (codePorte && scanRetinien) || clePorte || reinitialisationCode {
    println("Welcome !")
} else {
    println("ACCÈS REFUSÉ")
}// Affiche "Welcome !"
{% endhighlight swift linenos %}

Les parenthèses montrent plus clairement que les deux premières constantes sont considérée comme une expression à part entière de l'expression globale. Le résultat n'est pas affecté pour autant, l'expression est toujours <code>true</code>, néanmoins l'expression globale est beaucoup lisible ainsi.