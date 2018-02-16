#9.Modules
Depuis votre programme dans la fenêtre définition commencez par
\#lang slideshow

Tout le code que vous entrez dans la fenêtre de définition se situe à
l'intérieur d'un module. De plus, le module importe tout le contenu du
module dont le nom est slideshow, qui lui exporte les fonctions de création
d'images ainsi que des fonctions plus communéments utilisées tel que
'list' et 'map'.

Pour importer des librairies additionnelles, utilisez la syntaxe 'require'. Par exemple, la librairie 'pict/flash' donne accès à la fonction 'filled-flash':

(require pict/flash)

> (filled-flash 40 30)
Les modules sont nommés et distribués de plusieurs façons:

o Certains modules sont contenus dans la distribution Racket ou bien installés dans la hiérarchie
  des collections. Par exemple, le module nommé 'pict/flash' signifie "le module contenu dans
  le fichier 'flash.rkt' qui est situé dans la collection 'pict'".
  Quand le nom d'un module n'inclut pas de slash, alors il se réfère au fichier "main.rkt".

o Certaines collections de modules sont distribués comme des paquetages. Les paquetages
  peuvent être installés en cliquant sur le menu 'fichier' de DrRacket's puis
  'installer paquetage...'. les paquetages peuvent également être installés en utilisant
  l'outil ligne de commande "raco pkg". Par exemple, installer la paquetage "avl" rend le module
  avl disponible.

  Les paquetages peuvent être
