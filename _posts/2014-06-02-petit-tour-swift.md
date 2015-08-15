---
layout: post
title:  "Un petit tour de Swift"
date:   2015-06-20 15:51:51
categories: ['Bienvenue à SWIFT']
author: Guillaume L.
comments: True
permalink: /petit-tour-swift/
---

<div class="swift2">
	<p>Cette section a été relue et corrigée, elle prend maintenant en compte les modifications apportées avec <em>Swift 2</em>.</p>
</div>

**La tradition veut que lorsque l’on démarre l’apprentissage d’un nouveau langage l’on commence par le fameux *« Hello, World »*. Avec Swift, vous pouvez vous en sortir en seulement une seule ligne :**

{% highlight swift %}
print("Hello, world")
{% endhighlight %}

Si vous avez déjà écrit quelques lignes de code en C ou en Objective-C, cette syntaxe devrait vous sembler familière. Dans Swift, cette seule ligne de code est un programme complet. Vous n’avez pas besoin d’importer une librairie additionnelle pour des fonctionnalités comme *Input/Output* ou la gestion des *chaînes de caractères*. Le code est écrit de façon globale pour tout le programme et est utilisé comme point d’entrée pour le programme, du coup vous n’avez plus besoin de la fonction `main`. Vous n’avez également plus besoin d’ajouter une virgule ou un point-virgule à la fin d’une déclaration.

Ce petit tour vous donne assez d’information pour démarrer l’écriture du code avec Swift en présentant les différentes façons d’accomplir une très grande variété de tâches dans vos programmes. Pas d’inquiétude si vous ne comprenez pas tout dans ce chapitre, chaque élément sera expliqué en détail dans le reste de ce tutoriel.

>Pour une meilleure expérience, parcourez ce chapitre en exécutant **Xcode** en tâche de fond. Il vous permettra de tester les bouts de codes et d’apprécier leurs résultats immédiatement.

## Valeurs simples

Utilisez `let` pour initier une constante et `var` pour déclarer une variable. La valeur d’une constante n’a pas besoin d’être connue au moment de la compilation mais vous devez lui assigner une valeur exacte au départ. Ce qui signifie que vous pouvez utiliser les constantes pour nommer une valeur et l’utiliser ensuite à de nombreux endroits.

{% highlight swift linenos %}
var maVariable = 42
maVariable = 50
let maConstante = 42
{% endhighlight swift %}

Une constante ou une variable doivent avoir le même type que la valeur que vous lui assignez. Cependant, vous n’aurez pas toujours besoin d’indiquer le type de façon explicite. Fournir une valeur lorsque vous créez une constante ou une variable permet au compilateur de déduire son type. Dans l’exemple ci-dessus, le compileur sait que `maVariable` est un entier parce que sa valeur est un entier.

Si la valeur initiale ne présente pas suffisamment d’informations (ou bien qu’il n’y a pas de valeur initiale), vous devez spécifier le type en l’indiquant après la variable, séparé par deux points.

{% highlight swift linenos %}
let entierImplicite = 70
let DoubleImplicite = 70.0
let DoubleExplicite: Double = 70
{% endhighlight %}

>**Exercice :** Créez une constante avec le type explicite `Float` et la valeur 4. Quelle valeur obtenez-vous ?

Les valeurs ne sont jamais implicitement converties dans un autre type. Si vous avez besoin de convertir une valeur dans un autre type, vous devez explicitement créer une instance du type désiré.

{% highlight swift linenos %}
let label = "La largeur est "
let largeur = 94
let largeurTotale = label + String(largeur)
{% endhighlight %}

>**Exercice :** Essayer de supprimer le paramètre de conversion `String` de la dernière ligne. Quelle erreur obtenez-vous ?

Il y a une façon beaucoup plus simple de transformer les valeurs en chaîne de caractères : écrire la valeur entre parenthèses et précéder ces parenthèses d’un anti-slash. Par exemple :

{% highlight swift linenos %}
let pommes = 3
let oranges = 5
let pommesTotal = "Je possède \(pommes) pommes."
let fruitsTotal = "Je possède \(pommes + oranges) fruits en tout."
{% endhighlight %}

>**Exercice :** Utilisez () pour inclure une virgule flottante dans un calcul avec une chaîne de caractères.

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
let tableauVide = [String]()
let dictionnaireVide = [String:Float]()
{% endhighlight %}

Si le type de l’information peut être déduite par le compilateur, vous pouvez initier un tableau vide avec [] et un dictionnaire vide avec [:]

{% highlight swift linenos %}
shoppingList = []   // Je peux acheter n'importe quoi.
metiers = [:]
{% endhighlight %}

## Contrôle des flux

La gestion des conditions s’effectue avec `if` et `switch` et les boucles avec `for-in`, `for`, `while` et `repeat-while`. Les parenthèses autour des conditions et des boucles sont optionnelles. En revanche, les accolades autour du corps de la boucle ou de la condition sont indispensables.

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
print(equipeScore)
{% endhighlight %}

Dans le cas d’un `if`, la condition doit être une expression booléenne. Ce qui veut dire qu’un code du type `if score {...}` est une erreur, ce n’est pas une comparaison implicite à zéro.

Vous pouvez utiliser `if` et `let` ensemble pour pallier au problème. Ces valeurs sont présentées comme optionnelles. Une valeur optionnelle contient une valeur ou contient `nil` pour indiquer l’absence de valeur. Pour indiquer qu’une valeur est optionnelle, on utilise le point d’interrogation.

{% highlight swift linenos %}
var optionalString: String? = "Hello"
print(optionalString == nil)

var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
{% endhighlight %}

>**Exercice :** Changez `optionalName` par `nil`. Quelle salutation recevez-vous ? Ajoutez une clause `else` pour configurer une salutation différente si `optionalName` vaut `nil`.

Si la valeur optionnelle est `nil`, la condition est `false` et le code entre les accolades est ignoré. Par ailleurs, la valeur optionnelle est extraite et assignée à la constante après `let`, ce qui fait que la valeur devient disponible à l’intérieur du bloc de code.

Les `switch` supportent n’importe quel type de données et une grande variété d’opérateur de comparaison, ils ne sont pas uniquement limités aux entiers et aux tests d’égalité.

{% highlight swift linenos %}
let legume = "poivre rouge"
switch legume {
case "celeri":
    let commentaireLegume = "Ajouter quelques raisins."
case "concombre", "salade":
    let commentaireLegume = "Ça devrait faire un bon sandwich."
case let x where x.hasSuffix("poivre"):
    let commentaireLegume = "On sent les épices \(x)?"
default:
    let commentaireLegume = "Tout a bon goût dans la soupe."
}
{% endhighlight %}

>**Exercice :** Essayez d’enlever le `case` par défaut. Quelle erreur obtenez-vous ?

Après avoir exécuté le code dans le `switch case` qui a répondu, le programme sort de la boucle conditionnelle. L’exécution du programme ne continue pas avec le `case` suivant, il est donc inutile d’indiquer un `break` à la fin de chaque `case`.

Vous utiliserez `for-in` pour itérer (c’est à dire passer en revue) le contenu d’un dictionnaire en fournissant des noms à utiliser pour chaque paire de valeurs de clés.

{% highlight swift linenos %}
let nombresInterressants = [
    "Premier":      [2, 3, 5, 7, 11, 13],
    "Fibonacci":    [1, 1, 2, 3, 5, 8],
    "Carre":        [1, 4, 9, 16, 25],
]
var lePlusGrand = 0
for (type, nombres) in nombresInterressants {
    for nombreEnCours in nombres {
        if nombreEnCours > lePlusGrand {
            lePlusGrand = nombreEnCours
        }
    }
}
print(lePlusGrand)
{% endhighlight %}

>**Exercice :** Ajoutez une autre variable pour garder une trace du nombre qui était le plus grand, ainsi que le type du nombre que c’était.

Utilisez `while` pour répéter un bloc de code jusqu’à ce qu’une condition change. La condition de la boucle peut être à la fin, pour s’assurer l’exécution de la boucle au moins une fois.

{% highlight swift linenos %}
var n = 2
while n < 100 {
    n = n * 2
}
print(n)

var m = 2
repeat {
    m = m * 2
} while m < 100
print(m)
{% endhighlight %}

Vous pouvez garder un *index* dans la boucle. Soit en utilisant .. pour faire une « zone » d’index ou en écrivant explicitement l’initialisation, la condition et incrémentation ». La boucle ci-dessous est identique à la boucle plus haut :

{% highlight swift linenos %}
var premiereBoucleFor = 0
for i in 0..<4 {
    premiereBoucleFor += i
}
print(premiereBoucleFor)

var deuxiemeBoucleFor = 0
for var i = 0; i < 4; ++i {
    deuxiemeBoucleFor += 1
}
print(deuxiemeBoucleFor)
{% endhighlight %}

Utilisez `..<` pour faire une zone qui ne prend pas en compte le nombre le plus grand, et utilisez `...` pour une zone qui prend en compte les deux valeurs.

## Fonctions et closures

On utilise le mot clef `func`pour déclarer une *fonction*. Ensuite il suffit de lui donner un nom et des *arguments* entre parenthèses. On utilise `->`pour séparer les noms et types des paramètres du type de ce que retourne la fonction elle-même.

{% highlight swift linenos %}
func saluer(nom: String, jour: String) -> String {
	return "Bonjour \(nom), aujourd'hui nous sommes \(jour)."
}
saluer("Bob", "Mardi")
{% endhighlight swift linenos %}

>**Exercice :** Gardez le paramètre *jour*. Faites en sorte que la fonction *saluer* retourne l'heure du dîner en fonction du *jour*.

On utilise un *tuple* pour créer une valeur composée : par exemple, pour retourner plusieurs valeurs depuis une fonction. Les élements d'un *tuple* peuvent être référencés par nom ou par type.

{% highlight swift linenos %}
func calculsStatistiques(scores: [Int]) -> (min: Int, max: Int, total: Int) {
	var min = score[0]
	var max = score[0]
	var total = 0

	for score in scores {
		if score > max {
			max = score
		} else if score < min {
			min = score
		}
		total += score
	}

	return (min, max, total)
}
let statistiques = calculsStatistiques ([5, 3, 100, 3, 9])
print(statistiques.total)
print(statistiques.2)
{% endhighlight swift linenos %}

Les fonctions acceptent aussi que l'on fournisse un nombre variable d'arguments qui seront collectés via un tableau.

{% highlight swift linenos %}
func sommeDe(nombres: Int...) -> Int {
	var somme = 0
	for nombre in nombres {
		somme += nombre
	}
	return somme
}
sommeDe()
sommeDe(42, 597, 12)
{% endhighlight swift linenos %}

>**Exercice :** Écrivez une fonction qui retourne la moyenne d'un nombre indéfini de valeurs.

Les fonctions peuvent être imbriquées. Les fonctions imbriquées ont accès aux variables qui ont été déclarées en dehors de la fonction. Vous pouvez utiliser les fonctions imbriquées pour organiser un code long ou complexe.

{% highlight swift linenos %}
func retourneQuinze() -> Int {
	var y = 10
	func ajouter() {
		y += 5
	}
	ajouter()
	return y
}
retourneQuinze()
{% endhighlight swift linenos %}

Les fonctions ont un type de première classe. Ce qui signifie qu'une fonction peut retourner une autre fonction en tant que valeur.

{% highlight swift linenos %}
func creerIncrementeur() -> (Int -> Int) {
	func ajouterUn(nombre: Int) -> Int {
		return 1 + nombre
	}
	return ajouterUn
}
var incrementer = creerIncrementeur()
incrementer(7)
{% endhighlight swift linenos %}

Une fonction peut prendre une autre fonction comme un de ses arguments.

{% highlight swift linenos %}
func possedeLiens(liste: [Int], condition: Int -> Bool) -> Bool {
	for objet in liste {
		if condition(objet) {
			return true
		}
	}
	return false
}
func moinsQueDix(nombre: Int) -> Bool {
	return nombre < 10
}
var nombres = [20, 19, 7, 12]
possedeLiens(nombres, condition: moinsQueDix)
{% endhighlight swift linenos %}

Les *fonctions* sont en fait un cas spécial des *closures*: des blocs de code qui peuvent être appelés plus tard. Le code dans une *closure* a accès à des choses comme des variables et des fonctions qui étaient disponibles entre les accolades où ils ont été créés, même si la *closure* elle-même se trouve entre d'autres accolades lorsqu'elle est exécutée; nous l'avons vu avec l'exemple des *fonctions imbriquées*. Vous pouvez avoir une *closure* sans nom, simplement en entourant son code avec des parenthèses `({})`. Utilisez `in` pour séparer les arguments et retourner son type.

{% highlight swift linenos %}
nombres.map({
	(nombre: Int) -> Int in
	let resultat = 3 * nombre
	return resultat
})
{% endhighlight swift linenos %}

>**Exercice :** Réécrivez la closure pour qu'elle retourne zéro pour tous les nombres impairs.

Vous avez différentes options pour écrire une *closure* de façon plus concise. Lorsque le type d'une *closure* est déjà connu, vous n'êtes pas obligé d'indiquer son type dans les paramètres, le type retourné ou les deux. Les *closures* déclarées toutes seules retournent implicitement la valeur de leur propre déclaration.

{% highlight swift linenos %}
let nombresMap = nombres.map({ nombre in 3 * nombre })
print(nombreMap)
{% endhighlight swift linenos %}

Vous pouvez utiliser un nombre en paramètre plutôt qu'un nom : cette approche est spécialement utile pour les très courtes *closures*. Une *closure* passée en tant que dernier argument peut apparaître immédiatement après les parenthèses.

Lorsqu'une *closure* est le seul argument pour une fonction, vous pouvez ne pas mettre de parenthèses.

{% highlight swift linenos %}
let triNombre = nombres.tri { $0 > $1 }
print(triNombre)
{% endhighlight swift linenos %}

## Objets et classes













<div class="encours"><p>Ce chapitre est en cours de traduction, merci de revenir plus tard...</p></div>
