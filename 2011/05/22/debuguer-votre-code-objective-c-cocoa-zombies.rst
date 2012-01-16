public: yes
tags: [cocoa]

Débuguer votre code Objective-C Cocoa avec des Zombies
======================================================

Étant un newbie en Objective-C, il m’arrive assez souvent que mon application plante,
comme ça là, sans rien dire.

Après un peu de recherche, j’ai appris que le cas de figure le plus fréquent à ces
crashs est l’envoi d’un message à un objet désalloué en mémoire.

Pour faciliter le débugage de ce genre de cas, nous pouvons indiquer à notre appli
de ne pas desallouer les objets mais de les transformer en **Zombie** (yeeaaahhhhh).
Ainsi, un zombie qui reçoit un message répondra pas une erreur (genre : beeearrrrrgggghhhh)
et non pas par un crash de l’appli.

Pour activer les Zombies dans xcode, il suffit de double cliquer sur l’exécutable de notre
code et de se rendre dans l’ onglets Arguments et d’ajouter dans la liste Variables
to be set in the environment (en cliquant sur le + en bas de la fenêtre) la valeur
``NSZombieEnbaled`` avec la valeur ``YES``.

Comme les objets ne sont plus désalloués en mémoire, inutile de vous préciser que votre
application va en utiliser beaucoup et qu’il n’est pas recommandé de laisser ce paramètre
actif lors d’un test sur un iPhone ou pour la soumission à iTunes !

Source : `Cocoadev <http://www.cocoadev.com/index.pl?NSZombieEnabled>`_.
