---
layout: post
title:  "Guide de référence pour Swift"
date:   2015-06-20 12:58:51
categories: ['Annexes']
author: Guillaume L.
comments: True
permalink: /antiseche-swift/
---

<div class="swift2">
	<p>Cette section a été relue et corrigée, elle prend maintenant en compte les modifications apportées avec <em>Swift 2</em>.</p>
</div>

**Cette antisèche est un petit guide de références rapide autour du nouveau langage Swift d’Apple. Ce guide vise à couvrir toutes les fonctionnalités clé de Swift, y compris les chaînes, les tableaux, les dictionnaires et le contrôle des flux.**

Swift est un nouveau langage de programmation pour le développement d’applications iOS et OS X qui a été introduit par Apple en Juin 2014.

## Les variables

{% highlight swift %}
var monInt = 1
var monIntExplicite: Int = 1 // Type explicite
var x = 1, y = 2, z = 3 // Déclare plusieurs entiers
monIntExplicite = 2 // Change la valeur par un autre entier
{% endhighlight %}

## Les constantes

{% highlight swift %}
let monInt = 1
monInt = 2 // Erreur de compilation
{% endhighlight swift %}

## Les chaînes de caractères

{% highlight swift %}
var varChaine = "a"
let letChaine = "c"
varChaine += "b" // ab
varChaine = varChaine + letChaine // abc
letChaine += "d" // Erreur de compilation

let jours = 7
let message = "Il y à \(jours) jours dans une semaine"
{% endhighlight %}

## Opérateurs logiques

{% highlight swift %}
var heureux = true
var triste = !heureux // Opérateur NOT, triste = false
var toutLeMondeHeureux = heureux && triste
// Opérateur AND, toutLeMondeHeureux = false
var quelqunHeureux = heureux || triste // Opérateur OR, quelqunHeureux = true
{% endhighlight %}

## Imprimer à l’écran

{% highlight swift %}
let langage = "Swift"
print("Coucou")
print("J'utilise le langage \(langage)")
print("C'est vraiment ")
print("génial !")
// Coucou
// J'utilise le langage Swift
// C'est vraiment génial !
{% endhighlight %}

## Les tableaux

{% highlight swift %}
var couleurs = ["rouge", "bleu"]
var autresCouleurs: String[] = ["orange", "violet"] // type explicite
couleurs.append("vert") // [rouge, bleu, vert]
couleurs += "jaune" // [rouge, bleu, vert, jaune]
couleurs += autresCouleurs // [rouge, bleu, vert, jaune, orange, violet]

var jours = ["lun", "jeu"]
var premierJour = jours[0] // lun
jours.insert("mar", atIndex: 1) // [lun, mar, jeu]
jours[2] = "mer" // [lun, mar, mer]
jours.removeAtIndex(0) // [mar, mer]
{% endhighlight %}

## Les dictionnaires

{% highlight swift %}
var jours = ["lun": "lundi", "mar": "mradi"]
jours["mar"] = "mardi" // Change la valeur de la clé "mar"
jours["mer"] = "mercredi" // Ajoute une nouvelle clé et sa valeur

var autresJours: Dictionary = ["jeu": "jeudi", "ven": "vendredi"]
autresJours["jeu"] = nil // Retire jeudi du dictionnaire
autresJours.removeValueForKey("ven") // Retire vendredi du dictionnaire
{% endhighlight %}

## Les conditions

{% highlight swift %}
let content = true
if content {
    print("Je suis content !")
} else {
    print("Je suis triste...")
}
// Je suis content !

let vitesse = 28
if vitesse <= 0 {
    print("stationnement")
} else if vitesse <= 30 {
    print("vitesse réduite")
} else {
    print("trop rapide !")
}
// vitesse réduite

let n = 2
switch n {
case 1:
    print("C'est 1 !")
case 2...4:
    print("C'est entre 2 et 4 !")
case 5, 6:
    print("C'est 5 ou 6 !")
default:
    print("C'est un autre nombre !")
}
// C'est entre 2 et 4 !
{% endhighlight swift %}

## Les boucles *for*

{% highlight swift %}
for var index = 1; index < 3; ++index {
    // La boucle avec index prend les valeurs 1, 2
}
for index in 1..3 {
    // La boucle avec index prend les valeurs 1, 2
}
for index in 1...3 {
    // La boucle avec index prend les valeurs 1, 2, 3
}

let couleurs = ["rouge", "bleu", "jaune"]
for couleur in couleurs {
    print("Couleur : \(couleur)")
}
// Couleur : rouge
// Couleur : bleu
// Couleur : jaune

let jours = ["lun": "lundi", "mar": "mardi"]
for (miniJour, maxiJour) in jours {
    print("\(miniJour) est le nom court pour \(maxiJour)")
}
// lun est le nom court pour lundi
// mar est le nom court pour mardi
{% endhighlight swift %}

## Les boucles *while*

{% highlight swift %}
var compte = 1
while compte < 3 {
    print("Le compte vaut \(compte)")
    ++compte
}
// Le compte vaut 1
// Le compte vaut 2

compte = 1
while compte < 1 {
    print("Le compte vaut \(compte)")
    ++compte
}

compte = 1
repeat {
    print("Le compte vaut \(compte)")
    ++compte
} while compte < 3
// Le compte vaut 1
// Le compte vaut 2

compte = 1
repeat {
    print("Le compte vaut \(compte)")
    ++compte
} while compte < 1
// Le compte vaut 1
{% endhighlight swift %}

##Les fonctions

{% highlight swift %}
func fAjout(a: Int, b: Int) -> Int {
  return a + b
}
fAjout(2, 3) // retourne 5

func partEtAutre(n: Int) -> (nMoinsUn: Int, nPlusUn: Int) {
  return (n-1, n+1)
}
partEtAutre(5) // retourne le tuple (4,6)
{% endhighlight swift %}

## Les classes

{% highlight swift %}
class Compteur {
  var compte: Int = 0
  func incremente() {
    compte++
  }
  func ajoute(n: Int) {
    compte += n
  }
  func afficheCompte() {
    print("Compte : \(compte)")
  }
}

var monCompte = Compteur()
monCompte.incremente()
monCompte.ajoute(2)
monCompte.afficheCompte() // Compte : 3
{% endhighlight swift %}
