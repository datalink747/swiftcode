---
layout: post
title:  "Les assertions"
date:   2014-06-04 20:37:41
categories: ['Les Bases']
author: Guillaume L.
comments: True
permalink: /assertions/
---

**Les optionnelles vous autorisent à vérifier des valeurs qui peuvent exister ou ne pas exister, et à écrire du code qui fonctionne sans problème même lorsqu'il n'y a pas de valeurs.**

Dans certains cas néanmoins, il n'est simplement pas possible que votre code puisse continuer son exécution si aucune valeur n'existe, ou si vous n'avez pas fourni de valeur adéquate. Dans ces situations, vous pouvez déclencher une *assertion* dans votre code pour terminer son exécution et vous donner l'opportunité de le debugger à l'endroit où elle détecte une valeur manquante ou invalide.

## Debugger avec les assertions

Une assertion est une condition logique qui va stopper l'exécution de votre programme tant qu'elle ne sera pas <code>true</code>. Littéralement, écrire une assertion signifie qu'elle doit être forcement vraie. Vous utiliserez une assertion pour vous assurer qu'une condition est satisfaite avant d'exécuter la suite de votre programme. Si la condition est évaluée à <code>true</code>, l'exécution du code continue de façon totalement transparente. Si la condition est évaluée à <code>false</code>, l'exécution du code prend fin et votre application est stoppée.

Si votre code déclenche une assertion alors qu'il s'exécute dans un environnement de débogage, comme quand vous développez et testez votre application depuis Xcode, vous pourrez détecter exactement l'endroit précis qui pose problème, là où une valeur manquante ou invalide a été détecté pendant l'exécution du programme. Le message d'erreur provoqué par une assertion peut-être personnalisé et vous aider à corriger plus rapidement les problèmes.

Vous écrivez une assertion en appelant la fonction globale <code>assert</code>. Donnez ensuite à la fonction <code>assert</code> une expression à évaluer à <code>true</code> ou <code>false</code>, ainsi qu'un message qui ne sera affiché que lorsque que la condition sera à <code>false</code>.

{% highlight swift linenos %}
let age = -3
assert(age >= 0, "Une personne ne peut pas avoir un âge inférieur à zéro")
// Déclenche une assertion car l'âge est inférieur à 0
{% endhighlight swift  %}

Dans cet exemple, l'exécution du code ne continuera uniquement que si <code>age >= 0</code> est évalué à <code>true</code>, en gros, si la valeur de <code>age</code> c'est pas négative. Si la valeur de <code>age</code> est négative, comme dans le bout de code ci-dessus, alors la condition <code>age >= 0</code> est évaluée à <code>false</code> et l'assertion est déclenchée, l'application est stoppée.

Les messages d'assertion ne peuvent pas utiliser l'interpolation de chaînes de caractères. Le message d'assertion n'est pas obligatoire et peut-être oublié si désiré :

{% highlight swift linenos %}
assert(age >= 0)
{% endhighlight swift %}

## Quand utiliser les assertions ?

Utilisez les assertions lorsqu'une condition peu potentiellement être fausse et doit forcement être vraie pour que votre code puisse continuer de s'exécuter. Les scénarios appropriés à l'utilisation des assertions sont :

<ul><li>La valeur fournie peut être trop basse ou trop élevée</li>
<li>Une valeur est fournie à une fonction, mais la valeur est invalide</li>
<li>Une valeur optionnelle actuellement à <code>nil</code>, mais une valeur non nulle est requise</li></ul>

><u>Note :</u> Les assertions arrêtent votre application mais ne doivent pas être utilisées dans votre application finale, elles sont là uniquement durant le processus de développement pour accélérer les choses.