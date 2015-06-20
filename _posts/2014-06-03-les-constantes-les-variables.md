---
layout: post
title:  "Les constantes et les variables"
date:   2015-06-20 11:00:51
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /les-constantes-les-variables/
---

<div class="swift2">
	<p>Cette section a été relue et corrigée, elle prend maintenant en compte les modifications apportées avec <em>Swift 2</em>.</p>
</div>

**Les constantes et les variables sont associées à un nom (comme <code>nombreMaxLogin</code> ou <code>welcomeMessage</code> par exemple) avec une valeur et un type particulier (comme le nombre <code>10</code> ou la chaîne de caractères <code>"Hello"</code>). La valeur d'une _constante_ ne peut être modifiée une fois définie, sinon il s'agit d'une _variable_ et elle pourra prendre différentes valeurs dans le futur.**

## Déclarer les constantes et les variables

Les constantes et les variables doivent être déclarées avant d'être utilisées. On déclare les constantes avec le mot-clé <code>let</code> et les variables avec <code>var</code>. Voici un exemple qui montre comment les constantes et les variables peuvent être utilisées pour vérifier le nombre de tentatives de connexion d'un utilisateur sur votre application :

{% highlight swift linenos %}
let tentativesMaxLogin = 10
var tentativesLogin = 0
{% endhighlight swift linenos %}

Ce bout de code peut être lu de la façon suivante : *"Déclare une nouvelle constante appelée <code>tentativesMaxLogin</code>, et attribue lui la valeur <code>10</code>."*
*"Ensuite, déclare une nouvelle variable appelée <code>tentativesLogin</code>, et donne lui la valeur initiale <code>0</code>."*

Dans cet exemple, le nombre maximum de connexions autorisées est déclaré en tant que constante, parce-que ce nombre ne devra pas être amené à être changé. En revanche le compteur du nombre de tentatives de connexion est déclaré en tant que variable, puisque sa valeur sera incrémentée positivement après chaque échec de connexion.

Vous pouvez déclarer plusieurs constantes ou plusieurs variables en même temps sur une seule ligne en les séparant par des virgules :

{% highlight swift %}
var x = 0.0, y = 0.0, z = 0.0
{% endhighlight swift %}

>**Note :** Si vous stockez une valeur dans votre code qui ne sera pas amenée à changer, déclarez la toujours en tant que constante avec le mot-clé <code>let</code>. Utilisez les variables uniquement pour stocker des valeurs qui auront besoin de changer.

## Annotation des types

Vous pouvez indiquer le type de votre constante ou votre variable lorsque vous la déclarez, pour être clair avec les sortes de valeurs que vous souhaitez stocker. Pour indiquer le type d'une constante ou d'une variable, écrivez le type juste après son nom séparé par *deux points* et d'un espace.

Cet exemple montre une annotation de type pour une variable appelée <code>messageBienvenue</code> pour indiquer qu'il s'agit d'une chaîne de caractère (<code>String</code>) :

{% highlight swift %}
var messageBienvenue: String
{% endhighlight swift %}

Les deux points dans la déclaration veulent dire : *"...du type..."*, du coup le code ci-dessus peut-être lu comme ceci :

*"Déclare une variable appelée <code>messageBienvenue</code> qui est du type <code>String</code>."*

La phrase *"du type <code>String</code>"* veut dire *"peut stocker une valeur de type chaîne de caractères"*. C'est le *"type de chose"* qui peut être stocké. La variable <code>messageBienvenue</code> peut maintenant accueillir n'importe quelle chaîne de caractère sans erreur :

{% highlight swift %}
messageBienvenue = "Hello"
{% endhighlight swift %}

>**Note :** En réalité il est rare dans la pratique que vous ayiez à indiquer le type d'une variable ou d'une constante. En fournissant une valeur lors de la déclaration de votre constante ou de votre variable, Swift est capable de deviner son type. Les annotations de typages interviennent uniquement dans le cas d'une conversion ou de l'enregistrement d'une donnée ambigüe. Dans l'exemple ci-dessus avec la variable <code>messageBienvenue</code>, aucune valeur initiale n'est fournie, le type de la variable est alors spécifié avec une annotation, mais cette annotation aurait été inutile en fournissant une valeur initiale à la variable.

## Nommage des constantes et des variables

Vous pouvez utiliser n'importe quel caractère pour vos noms de variables et de constantes, même les caractères spéciaux et unicode :

{% highlight swift linenos %}
let π = 3.14159
let 你好 = "你好世界"
let 💋💖 = "bisoucoeur"
{% endhighlight swift linenos %}

Les noms des constantes et des variables ne peuvent pas contenir de symboles mathématiques, de flèches, de code Unicode invalide ni de points. Ils ne peuvent pas non plus commencer par un chiffre mais il est possible d'inclure des chiffres dans le nom de variables et des constantes n'importe où ailleurs dans leurs noms.

Une fois que vous avez déclaré une contante ou une variable d'un certain type, vous ne pouvez plus utiliser son nom pour en déclarer une autre ou changer le type de valeur qui y sont stockées. Vous ne pouvez pas non plus changer une constante en variable et une variable en constante.

>**Note :** Si vous avez besoin de donner à une constante ou une variable le même nom qu'un mot-clé Swift réservé, vous pouvez le faire en entourant le mot-clé avec des guillemets inversés quand vous l'utilisez en tant que nom. Néanmoins vous ne devriez utiliser cette solution que dans la mesure où vous n'avez vraiment pas le choix.

Vous pouvez change la valeur d'une variable existante par une autre valeur d'un type compatible. Dans l'exemple ci-dessous, la valeur de <code>bonjourAmical</code> est passée de <code>"Hello!"</code> à <code>"Bonjour!"</code> :

{% highlight swift linenos %}
var bonjourAmical = "Salut!"
bonjourAmical = "Bonjour!"
// bonjourAmical vaut maintenant "Bonjour!"
{% endhighlight swift linenos %}

Contrairement aux variables, la valeur d'une constante ne peut pas être modifiée une fois qu'elle a été définie. Si vous tentez de changer la valeur d'une constante vous vous exposez à une erreur au moment de la compilation :

{% highlight swift linenos %}
let nomLangage = "Swift"
nomLangage = "Swift 2"
// Error - nomLangage cannot be changed
{% endhighlight swift linenos %}

## Afficher les constantes et les variables

Vous pouvez afficher la valeur courante d'une constante ou d'une variable avec la fonction `print(_:)` :

{% highlight swift linenos %}
print(bonjourAmical)
// Affichera à l'écran "Bonjour!"
{% endhighlight swift linenos %}

`print(_:)` est une fonction globale qui affiche une valeur, suivie d'un retour à la ligne, à la sortie appropriée. Si vous travaillez depuis Xcode, par exemple, `print(_:)` affichera la valeur demandée dans la console Xcode. Une fonction liée, `print(_:appendNewline:)`, réalise exactement la même opération mais sans le retour à la ligne après l'affichage de la valeur.

La fonction `print(_:)` affiche n'importe quelle chaîne de caractères qu'on lui fournit :

{% highlight swift linenos %}
print("Ceci est une chaîne de caractères")
// Affiche "Ceci est une chaîne et caractères"
{% endhighlight swift linenos %}

La fonction `print(_:)` peut afficher des messages de logs plus complets. Ces messages peuvent inclure les valeurs de contantes ou de variables.

Swift convertit systématiquement les valeurs incluses dans les variables et les constantes en chaîne de caractères pour s'afficher dans la console Xcode avec `print(_:)`. Il est possible d'afficher une chaîne de caractères avec une variable ou une constante en précédant son nom d'un anti-slash et en l'entourant de parenthèses :

{% highlight swift linenos %}
print("La valeur actuelle de bonjourAmical est \(bonjourAmical)")
// Affiche "La valeur actuelle de bonjourAmical est Bonjour!"
{% endhighlight swift linenos %}

>**Note :** Toutes les options que vous pouvez utiliser sont expliquées plus en détails dans la partie *Interpolation des chaînes de caractères*.
