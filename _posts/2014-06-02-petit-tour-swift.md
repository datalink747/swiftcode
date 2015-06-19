---
layout: post
title:  "Un petit tour de Swift"
date:   2014-06-02 12:58:51
categories: ['Bienvenue à SWIFT']
author: Guillaume L.
comments: True
permalink: /petit-tour-swift/
---

**La tradition veut que lorsque l’on démarre l’apprentissage d’un nouveau langage l’on commence par le fameux *« Hello, World »*. Avec Swift, vous pouvez vous en sortir en seulement une seule ligne :**

{% highlight swift %}
println("Hello, world")
{% endhighlight %}

Si vous avez déjà écrit quelques lignes de codes en C ou en Objective-C, cette syntaxe devrait vous sembler familière. Dans Swift, cette seule ligne de code est un programme complet. Vous n’avez pas besoin d’importer une librairie additionnelle pour des fonctionnalités comme *Input/Output* ou la gestion des *chaînes de caractères*. Le code est écrit de façon globale pour tout le programme et est utilisé comme point d’entrée pour le programme, du coup vous n’avez plus besoin de la fonction `main`. Vous n’avez également plus besoin d’ajouter une virgule ou un point-virgule à la fin d’une déclaration.

Ce petit tour vous donne assez d’information pour démarrer l’écriture du code avec Swift en présentant les différentes façons d’accomplir une très grande variété de tâches dans vos programmes. Pas d’inquiétude si vous ne comprenez pas tout dans ce chapitre, chaque élément sera expliqué en détail dans le reste de ce tutoriel.

>Pour une meilleure expérience, parcourez ce chapitre en exécutant **Xcode** en tâche de fond. Il vous permettra de tester les bouts de codes et d’apprécier leurs résultats immédiatement.

## Valeurs simples

Utilisez `let` pour initier une constante et `var` pour déclarer une variable. La valeur d’une constante n’a pas besoin d’être connue au moment de la compilation mais vous devez lui assigner une valeur exacte au départ. Ce qui signifie que vous pouvez utiliser les constantes pour nommer une valeur et l’utiliser ensuite à de nombreux endroits.

{% highlight swift linenos %}
var maVariable = 42
maVariable = 50
let maConstante = 42
{% endhighlight swift %}

Une constante ou une variable doivent avoir le même type que la valeur que vous lui assignez. Cependant, vous n’aurez pas toujours besoin d’indiquer le type de façon explicite. Fournir une valeur lorsque vous créez une constante ou une variable permet au compilateur de déduire son type. Dans l’exemple ci-dessus, le compileur sait que `maVariable` est un intégral parce-que sa valeur est un intégral (un nombre entier).

Si la valeur initiale ne présente pas suffisamment d’information (ou bien qu’il n’y a pas de valeur initiale), vous devez spécifiez le type en l’indiquant après la variable, séparé par deux points.

{% highlight swift linenos %}
let impliciteIntegral = 70
let impliciteDouble = 70.0
let expliciteDouble: Double = 70
{% endhighlight %}

>**Exercice :** Créez une constante avec le type explicite `Float` et la valeur 4. Quelle valeur obtenez-vous ?

Les valeurs ne sont jamais implicitement converties dans un autre type. Si vous avez besoin de convertir une valeur dans un autre type, vous devez explicitement créer une instance du type désiré.

{% highlight swift linenos %}
let label = "La largeur est "
let largeur = 94
let largeurTotale = label + String(largeur)
{% endhighlight %}

>**Exercice :** Essayer de supprimer le paramètre de conversion `String` de la dernière ligne. Quelle erreur obtenez-vous ?

Il y a une façon beaucoup plus simple de transformer les valeurs en chaîne de caractères : Écrire la valeur entre parenthèses et précéder ces parenthèses d’un anti-slash. Par exemple :

{% highlight swift linenos %}
let pommes = 3
let oranges = 5
let pommesTotal = "Je possède \(pommes) pommes."
let fruitsTotal = "Je possède \(pommes + oranges) fruits en tout."
{% endhighlight %}

>**Exercice :** Utilisez () pour inclure une virgule flottante dans un calcul avec une chaîne de caractère.

On utilise les crochets ([ ]) pour créer des tableaux et des dictionnaires, et on accède à leurs éléments en indiquant la clé ou l’index entre crochets.

{% highlight swift linenos %}
var shoppingList = ["poisson", "eau", "tulipes", "peinture bleue"]
shoppingList[0] = "Saumon"
shoppingList[1] = "bouteilles de Vittel"

var metiers = [
    "Alexandre": "Capitaine",
    "Kevin": "Mécano",
]

metiers["Jeanne"] = "Relations publiques"
{% endhighlight %}

Pour créer un tableau ou un dictionnaire vide, utilisez la syntaxe d’initialisation.

{% highlight swift linenos %}
let nouveauTableau = String[]()
let nouveauDictionnaire = Dictionary<String, Float>()
{% endhighlight %}

Si le type de l’information peut être déduite par le compileur, vous pouvez initier un tableau vide avec [ ] et un dictionnaire vide avec [ : ]

{% highlight swift linenos %}
shoppingList = []   // Je peux acheter n'importe quoi.
{% endhighlight %}

## Controle des flux

La gestion des conditions s’effectue avec `if` et `switch` et les boucles avec `for-in`, `for`, `while` et `do-while`. Les parenthèses autour des conditions et des boucles sont optionnelles. En revanche, les accolades autour du corps de la boucle ou de la condition sont indispensables.

{% highlight swift linenos %}
let individuelScore = [75, 43, 103, 87, 12]
var equipeScore = 0
for score in individuelScore {
    if score > 50 {
        equipeScore += 3
    } else {
        equipeScore += 1
    }
}
equipeScore
{% endhighlight %}

Dans le cas d’un `if`, la condition doit être une expression booléenne. Ce qui veut dire qu’un code du type `if score {...}` est une erreur, ce n’est pas une comparaison implicite à zéro.

Vous pouvez utiliser `if` et `let` ensemble pour pallier au problème. Ces valeurs sont présentés comme optionnelles. Une valeur optionnelle contient une valeur ou contient `nil` pour indiquer l’absence de valeur. Pour indiquer qu’une valeur est optionnelle, on utilise le point d’interrogation.

{% highlight swift linenos %}
var optionalString: String? = "Hello"
optionalString == nil
 
var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
{% endhighlight %}

>**Exercice :** Changez `optionalName` par `nil`. Quelle salutation recevez-vous ? Ajoutez une clause `else` pour configurer une salutation différente si `optionalName` vaut `nil`.

Si la valeur optionnelle est `nil`, la condition est `false` et le code entre les accolades est ignoré. Par ailleurs, la valeur optionnelle est extraite et assignée à la constante après `let`, ce qui fait que la valeur devient disponible à l’intérieur du bloc de code.

Les `switch` supportent n’importe quel type de données et une grande variété d’opérateur de comparaison, ils ne sont pas uniquement limités aux intégrales et aux tests d’égalités.

{% highlight swift linenos %}
let vegetable = "poivre rouge"
switch vegetable {
case "céleri":
    let vegetableComment = "Ajouter quelques raisins."
case "concombre", "salade":
    let vegetableComment = "Ça devrait faire un bon sandwich."
case let x where x.hasSuffix("poivre"):
    let vegetableComment = "On sent les épices \(x)?"
default:
    let vegetableComment = "Tout a bon goût dans la soupe."
}
{% endhighlight %}

>**Exercice :** Essayez d’enlever le `case` par défaut. Quelle erreur obtenez-vous ?

Après avoir exécuté le code dans le `switch case` qui a répondu, le programme sort de la boucle conditionnelle. L’exécution du programme ne continue pas avec le `case` suivant, il est donc inutile d’indiquer un `break` à la fin de chaque `case`.

Vous utiliserez `for-in` pour itérer (c’est a dire passer en revue) le contenu d’un dictionnaire en fournissant des noms a utiliser pour chaque paire de valeurs de clés.

{% highlight swift linenos %}
let nombreInterressant = [
    "Premier":      [2, 3, 5, 7, 11, 13],
    "Fibonacci":    [1, 1, 2, 3, 5, 8],
    "Carre":        [1, 4, 9, 16, 25],
]
var lePlusGrand = 0
for (kind, numbers) in nombreInterressant {
    for nombreEnCours in numbers {
        if nombreEnCours > lePlusGrand {
            lePlusGrand = nombreEnCours
        }
    }
}
lePlusGrand
{% endhighlight %}

>**Exercice :** Ajoutez une autre variable pour garder une trace du nombre qui était le plus grand, ainsi que le type du nombre que c’était.

Utilisez `while` pour répéter un bloc de code jusqu’a ce qu’une condition change. La condition de la boucle peut être à la fin, pour s’assurer l’exécution de la boucle au moins une fois.

{% highlight swift linenos %}
var n = 2
while n < 100 {
    n = n * 2
}
n
 
var m = 2
do {
    m = m * 2
} while m < 100
m
{% endhighlight %}

Vous pouvez garder un *index* dans la boucle. Soit en utilisant .. pour faire une « zone » d’index ou en écrivant explicitement l’initialization, la condition et incrémentation ». La boucle ci-dessous est identique à la boucle plus haut :

{% highlight swift linenos %}
var firstForLoop = 0
for i in 0..3 {
    firstForLoop += i
}
firstForLoop
 
var secondForLoop = 0
for var i = 0; i < 3; ++i {
    secondForLoop += 1
}
secondForLoop
{% endhighlight %}

Utilisez `..` pour faire une zone qui ne prend pas en compte le nombre le plus grand, et utilisez `...` pour une zone qui le prend en compte.