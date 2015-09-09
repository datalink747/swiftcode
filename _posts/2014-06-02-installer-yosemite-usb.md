---
layout: post
title:  "Installer OSX 10.10 Yosemite"
date:   2014-06-02 12:58:51
categories: ['Annexes']
author: Guillaume L.
comments: True
permalink: /installer-yosemite-depuis-cle-usb/
---

**Pour démarrer correctement votre apprentissage du langage Swift il va falloir pouvoir lancer Xcode 6 sur son Mac. Pour ce faire il faut au préalable que vous ayez installé Mac OS X 10.10 en tant que nouveau système d’exploitation puisqu’il est le seul à ce jour à reconnaitre les applications développées avec Swift et aussi parce que Xcode 6 refuse de s’installer sur une version antérieure.**

## Mise à jour de Mavericks vers Yosemite

La méthode la plus simple est encore de se laisser guider pas à pas par l’installateur Apple et de jouer la carte de la facilité. Néanmoins, aucune version stable de Yosemite n’est encore sortie pour le commun des utilisateurs, il va donc falloir ruser et utiliser une version préliminaire spécialement accessible aux développeurs.

Si vous n’avez pas de compte développeur, sachez que vous pouvez quand même vous procurer la dernière version du système Mac OS X 10.10 Yosemite sur notre site en cliquant ici. Pour faciliter les choses nous n’avons mis à disposition que le fichier *InstallESD.dmg* qui permet d’installer tout le système de différentes manières.

Cette fois-ci vous ne pouvez pas passer par le Mac AppStore mais en montant cette image sur votre Mac vous allez pouvoir exécuter Yosemite et démarrer l’installation. Montez le fichier *InstallESD.dmg* et ensuite montez le fichier *BaseSystem.dmg* qui se trouve à l’intérieur. Vous devriez alors voir dans cette dernière image une petite icône pour lancer l’installation de Yosemite !

![Installation Yosemite](/img/Capture-d’écran-2014-06-04-à-22.23.50.png)

## Installer Mac OSX 10.10 Yosemite depuis une clé USB bootable

La première étape est d’afficher les fichiers système cachés. Pour ce faire ouvrez le terminal et exécutez les commandes suivantes :

{% highlight bash linenos %}
defaults write com.apple.Finder
AppleShowAllFiles YES
killall Finder
{% endhighlight %}

Préparez ensuite une clé USB de 8 Go au moins pour être sûr que tout rentre parfaitement. 4 Go risque d’être trop juste puisque l’image compressée fait déjà 5,09 Go. Montez ensuite votre image *InstallESD.dmg* fraichement téléchargée sur votre disque.

Si vous avez suivi correctement la première étape vous devriez voir les fichiers cachés de cette image, ils sont légèrement plus opaques que les autres. Parmi eux se trouve une autre image nommée *BaseSystem.dmg* qu’il va falloir restaurer sur la clé USB grâce à l’utilitaire de disque.

Votre clé USB est maintenant restaurée et s’appelle *OS X Base System*, ouvrez-la. Naviguez dans *System/Installation*, vous devriez voir un raccourci vers *Packages*. Supprimez ce raccourci et copiez le vrai dossier *Packages* qui se trouve à la racine de l’image *InstallESD.dmg* au même endroit. Voilà votre clé USB est prête.

Pour démarrer sur cette clé USB, redémarrez votre Mac et maintenez la touche <kbd>ALT</kbd> enfoncée à partir du démarrage de l’ordinateur. Vous devriez normalement pouvoir sélectionner votre clé USB et lancer l’installation de Yosemite. Pour la suite, rien de compliqué, il suffit de suivre les étapes une par une jusqu’à la fin de l’installation.

>**Note :** Pensez tout de même à sauvegarder vos données avant ce type de formatage, pour éviter de perdre des fichiers importants !

Si vous souhaitez cacher de nouveau les fichiers système, relancer les commandes de la première étape dans votre terminal en remplaçant à la deuxième ligne le *YES* par un *NO*.

## Installer Yosemite sur une autre partition en dualboot

Pour éviter les déboires des versions beta : bugs, instabilités et incompatibilités, il est préférable de redimensionner sa partition principale pour laisser un peu de place à une seconde partition qui pourra alors accueillir Yosemite.

Si vous êtes ici depuis le début de ce tutoriel, vous avez probablement la majorité des clés en main pour réussir l’opération. Il vous faudra préparer une clé USB bootable de Yosemite (cf. voir plus haut), et accéder à votre partition principale pour la redimensionner. Pour la clé USB bootable, suivez les instructions décrites plus haut, le liens pour télécharger Yosemite Developper Preview est disponible ici.

Pour redimensionner votre partition principale, ouvrez l’utilitaire de disque, sélectionner votre disque principal et rendez-vous sur l’onglet *« Partition »*. Appuyez sur le + en bas de la partition pour créer une nouvelle partition et redimensionner la principale. Prévoyez au minimum 15 Go, et 35 Go pour être confortable. Adaptez en fonction des capacités de votre disque dur.

![Partition Yosemite](/img/make-a-partition-for-yosemite.jpg)

Il suffit ensuite de lancer l’installation de Yosemite depuis l’installateur officiel ou depuis votre clé USB en redémarrant sur celle-ci avec la touche <kbd>ALT</kbd>. Sélectionnez la partition que vous venez de créer et installer normalement Yosemite en suivant les instructions à l’écran.

Une fois l’installation terminée, il vous suffira de presser <kbd>ALT</kbd> à chaque démarrage de votre machine pour sélectionner la partition sur laquelle vous souhaitez booter !
