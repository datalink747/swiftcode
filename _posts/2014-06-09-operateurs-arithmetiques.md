---
layout: post
title:  "Opérateurs arithmétiques"
date:   2014-06-09 23:49:43
categories: ['Les opérateurs']
author: Guillaume L.
comments: True
permalink: /operateurs-arithmetiques/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Swift supporte quatre *opérateurs arithmétiques* standards pour tous les types de nombres :**

<ul><li>Les additions (<code>+</code>)</li>
<li>Les soustractions (<code>-</code>)</li>
<li>Les multiplications (<code>*</code>)</li>
<li>Les divisions (<code>/</code>)</li></ul>

{% highlight swift linenos %}
1 + 2         // égal à 3
5 - 3         // égal à 2
2 * 3         // égal à 6
10.0 / 2.5    // égal à 4.0
{% endhighlight swift linenos %}

Contrairement aux opérateurs arithmétiques en C et en Objective-C, les opérateurs arithmétiques du langage Swift ne permettent pas aux valeurs de déborder par défaut. Pour réaliser ce type d'opération, vous devrez utiliser les opérateurs de débordement (comme dans <code>a &+ b</code>). Voir la partie *Opérateurs de débordement*.

L'opérateur d'addition est aussi supporté pour la concaténation entre chaîne de caractères :

{% highlight swift %}
"hello, " + "world" // égal à "hello, world"
{% endhighlight swift %}

Il est possible d'utiliser des valeurs de types <code>character</code>, comme des émoticones avec les opérateurs numériques. Ils répondent aux même règles que les chaînes de caractères.

## La division avec reste

L'opérateur numérique qui sert a effectuer des divisions avec reste correspond au signe *pourcentage* sur votre clavier (%). dans l'opération <code>a % b</code>, la division avec reste permet de calculer combien de multiple de <code>b</code> se trouve dans <code>a</code> et ensuite de retourner le restant indivisible (le reste).

><u>Note :</u> L'opérateur de division avec reste est aussi connu sous le nom d'*opérateur modulo* dans d'autres langages. Toutefois, son comportement dans Swift pour les nombres négatifs signifie qu'il est à proprement parlé, un reste plutôt qu'une opération de type *modulo*.

Voilà comment la division avec reste fonctionne. Pour calculer <code>9 % 4</code>, la première chose à faire de savoir combien de fois le chiffre <code>4</code> rentre entièrement dans l'entier <code>9</code> :

![Division avec reste](/img/Capture-d’écran-2014-06-14-à-13.20.05.png)

On peut mettre deux fois <code>4</code> à l'intérieur <code>9</code>, et il reste <code>1</code>, indivisible par le chiffre <code>4</code> (en orange). Dans Swift on pourrait l'écrire :

{% highlight swift %}
9 % 4    // égal à 1
{% endhighlight swift %}

Pour déterminer la réponse de <code>a % b</code>, l'opérateur de division avec reste calcule l'équation ci-dessous et retourne le reste :

{% highlight swift %}
a = ( b * multiplicateur ) + reste
{% endhighlight swift %}

Lorsque le multiplicateur est le nombre le plus large des multiples de <code>b</code> il est indiqué dans <code>a</code>. Insérez <code>9</code> dans l'équation pour vérifier :

{% highlight swift %}
9 = ( 4 * 2 ) + 1
{% endhighlight swift %}

La même méthode est appliquée lorsque vous calculez le reste d'une valeur négative de <code>a</code> :

{% highlight swift %}
-9 % 4   // égal à -1
{% endhighlight swift %}

{% highlight swift %}
-9 = ( 4 * -2 ) + -1   // le reste vaut -1
{% endhighlight swift %}

Le signe de <code>b</code> est ignoré pour les valeurs négatives de <code>b</code>. Ce qui signifie que <code>a % b</code> et <code>a % -B</code> donneront toujours le même résultat.

## Calculer le reste avec des nombres à virgule

Contrairement à l'opérateur de division avec reste en C et en Objective-C, Swift permet d'effectuer ce genre d'opération avec des nombres à virgule :

{% highlight swift %}
8 % 2.5  // égal à 0,5
{% endhighlight swift %}

Dans cet exemple, <code>8</code> divisé par <code>2.5</code> vaut <code>3</code>, et il reste <code>0.5</code>. L'opérateur numérique retourne une valeur du type <code>Double</code>.

![Calculer le reste des nombres](/img/Capture-d’écran-2014-06-20-à-11.09.00.png)

## Opérateurs d'incrémentation et de décrémentation 

Comme en C, Swift dispose d'un opérateur d'incrémentation (<code>++</code>) un d'un opérateur de décrémentation (<code>--</code>) agissant comme des raccourcis pour augmenter ou diminuer la valeur d'une variable numérique par <code>1</code>. Vous pouvez utiliser ces opérateurs avec des variables de n'importe n'importe quel type numérique.

{% highlight swift linenos %}
var i = 0
++i    // i vaut maintenant 1
{% endhighlight swift linenos %}

Chaque fois que vous appelez <code>i++</code>, la valeur de <code>i</code> est incrémentée de <code>1</code>. Essentiellement, <code>i++</code> est un raccourcis pour l'opération <code>i = i + 1</code>. Du coup, <code>i--</code> peut être utilisé comme raccourcis pour <code>i = i - 1</code>.

Les symboles <code>++</code> et <code>--</code> peuvent être utilisés comme préfixe ou comme suffixe. <code>++i</code> et <code>i++</code> sont deux solutions valides pour incrémenter la valeur de <code>i</code> par <code>1</code>. Idem avec l'opérateur <code>--</code>, qui peut se placer avant ou après la variable concernée pour décrémenter une valeur.

Notez que ces opérateurs modifient <code>i</code> et retournent systématiquement une valeur. Si vous voulez juste incrémenter ou décrémenter la valeur stockée dans <code>i</code>, vous pouvez ignorer la nouvelle valeur retournée. Il faut aussi savoir que si l'opérateur est placé *avant* la variable, il incrémente la variable *avant* de retourner sa valeur. S'il est placé *après*, il incrémente la variable *après* avoir retourné sa valeur. Par exemple :

{% highlight swift linenos %}
var a = 0
letb = ++a
// a et b valent maintenant tous les deux 1
letc = a++
// a est maintenant égal à 2, mais c a été initialisé avec la valeur 1
{% endhighlight swift linenos %}

Dans l'exemple ci-dessus, <code>let b = ++a</code> incrémente <code>a</code> *avant* de retourner sa valeur. Voilà pourquoi <code>a</code> et <code>b</code> valent tous les deux <code>1</code>.

Cependant, <code>let c = a++</code> incrémente <code>a</code> *après* avoir retourné sa valeur. Donc <code>c</code> est initialisé avec l'ancienne valeur de <code>a</code> et récupère la valeur <code>1</code>. Ensuite <code>a</code> est incrémenté et vaut au final <code>2</code>.

A moins que vous en ayiez vraiment besoin, il est recommandé d'utiliser <code>++i</code> et <code>--i</code> dans tous les cas, afin d'éviter les confusions et les erreurs de valeurs.

## Opérateur unaire "Moins"

Le symbole numérique <code>-</code> utilisé normalement pour les opérations numériques comme la soustraction peut aussi être utilisé comme *opérateur unaire* devant une variable ou une constante de type numérique :

{% highlight swift linenos %}
let trois = 3
let moinsTrois = -trois  // moinsTrois vaut -3
let plusTrois = -moinsTrois  // plusTrois vaut 3 (--3)
{% endhighlight swift linenos %}

Cet opérateur unaire est mit directement avant la valeur sur laquelle il faut opérer, sans espace.

## Opérateur unaire "Plus"

Comme l'opérateur unaire précédent, il existe aussi la version normalement utilisée avec les additions qui, devant une variable ou une constante de type numérique, retourne simplement la valeur sans aucun changement :

{% highlight swift linenos %}
let moisHuit = -8
let tjsMoinsHuit = +moinsHuit    // tjsMoinsHuit vaut -8 (+-8)
{% endhighlight swift linenos %}

L'opérateur unaire <code>+</code> ne sert pas à grand chose en fait. Vous pouvez l'utiliser pour permettre une meilleure compréhension de votre code mais il est totalement facultatif.