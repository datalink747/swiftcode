---
layout: post
title:  "Les chaînes de caractères littérales"
date:   2014-06-09 23:50:50
categories: ['Les chaînes']
author: Guillaume L.
comments: True
permalink: /les-chaines-litterales/
---

<div class="swift1">
	<p>Cette documentation est encore en cours de rédaction chez <em>Apple</em> et des corrections peuvent être apportées au cours des semaines à venir.</p>
</div>

**Vous pouvez prédéfinir à l'avance les valeurs de type <code>String</code> en indiquant une suite de chiffre ou de lettres entourées par des guillemets (<code>"  "</code>).**

Une chaîne de caractères peut être utilisée pour fournir une valeur initiale à une constante ou une variable :

{% highlight swift %}
var uneChaine = "Une chaine de caractères"
{% endhighlight swift%}

Noter que Swift devine le type <code>String</code> pour la variable <code>uneChaine</code> parce qu’elle a été initialisée avec une chaîne de caractères littérale.

Les chaînes de caractères peuvent inclure les caractères spéciaux suivants :
<ul><li>Les caractères spéciaux <em>"échappés"</em> : <code>\0</code> (caractère nul), <code>\\</code> (antislash), <code>\t</code> (tabulation horizontale), <code>\n</code> (saut de ligne), <code>\r</code> (retour en début de ligne), <code>\"</code> (guillemet) et <code>\'</code> (apostrophe)</li>
<li>Un octet scalaire Unicode, écrit comme <code><strong>\x</strong>nn</code>, où <code>nn</code> sont deux chiffres hexadécimaux.</li>
<li>Deux octets scalaires Unicode, écrit comme <code><strong>\u</strong>nnnn</code>, où <code>nnnn</code> son quatre chiffres hexadécimaux.</li>
<li>Quatre octets scalaires Unicode, écrit comme <code><strong>\U</strong>nnnnnnnn</code>, où <code>nnnnnnnn</code> son huit chiffres hexadécimaux.</li></ul>

Le code ci-dessous montre un exemple de chaque sorte de caractères spéciaux. La constante <code>motSavant</code> contient deux caractères spéciaux *"échappés"*. Les constantes <code>signeDollar</code>, <code>coeurNoir</code>  et <code>coeurScintillant</code> montrent que les trois formats différents de caractères scalaires Unicode :

{% highlight swift linenos %}
let motSavant = "\"L'imagination est plus importante que la connaissance\" - Einstein"
let signeDollar = "\x24"     // scalaire Unicode $ (U+0024)
let coeurNoir = "\u2666"     // scalaire Unicode ♥ (U+2666)
let coeurScintillant = "\U0001F476"  // scalaire Unicode  (U+1F476)
{% endhighlight swift linenos %}

><u>Note :</u> Pour plus d’information sur les Octets scalaires, nous vous renvoyons sur le site : <a href="http://www.ascii-code.com" title="Unicode" target="_blank">http://www.ascii-code.com</a> ou vous trouverez tous les caractères spéciaux au format Decimal, Octal (celui que nous venons de voir), Hexadecimal, Binaire, Symbolique et HTML.