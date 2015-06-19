---
layout: post
title:  "Modifier une chaîne de caractères"
date:   2014-06-09 23:52:52
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /modifier-chaine-swift/
---

**Pour indiquer si une chaîne peut être modifiée assignez-là à une variable (dans ce cas elle peut être modifiée), ou à une constante (dans ce cas là ne peut pas être modifiée) :**

{% highlight swift linenos %}
var chaineVariable = "Chevaux"
chaineVariable += " et poneys"
// chaineVariable vaut maintenant "Chevaux et poneys"

let chaineConstante = "Timon"
chaineConstante += " et Pumba" 
// Le compilateur rapporte une erreur : un constante ne peut pas être modifiée
{% endhighlight swift linenos %}

><u>Note :</u> Cette approche est différente des chaînes modifiables en Objective-C et Cocoa, ou vous pouviez choisir entre deux classes (<code>NSString</code> et <code>NSMutableString</code>) pour indiquer si une chaîne peut être modifiée.