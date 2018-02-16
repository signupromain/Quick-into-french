## 9Modules
Depuis votre programme dans la fenêtre définition commencez par 

```racket
\#lang slideshow
```
Tout le code que vous entrez dans la fenêtre de définition se situe à 
l'intérieur d'un module. De plus, le module importe tout le contenu du 
module dont le nom est 'slideshow', qui lui exporte les fonctions de création 
d'images ainsi que des fonctions plus communéments utilisées tel que
'list' et 'map'.

Pour importer des librairies additionnelles, utilisez la syntaxe 'require'. Par exemple, la librairie 'pict/flash' donne accès à la fonction 'filled-flash':

```racket
(require pict/flash)

> (filled-flash 40 30)
```


Les modules sont nommés et distribués de plusieurs façons:

* Certains modules sont contenus dans la distribution Racket ou bien installés dans la hiérarchie
  des collections. Par exemple, le module nommé 'pict/flash' signifie "le module contenu dans
  le fichier 'flash.rkt' qui est situé dans la collection 'pict'".
  Quand le nom d'un module n'inclut pas de slash, alors il se réfère au fichier "main.rkt".

* Certaines collections de modules sont distribués comme des paquetages. Les paquetages
  peuvent être installés en cliquant sur le menu 'fichier' de DrRacket's puis
  'installer paquetage...'. les paquetages peuvent également être installés en utilisant 
  l'outil ligne de commande "raco pkg". Par exemple, installer la paquetage "avl" rend le module 
  avl disponible.

  Les paquetages peuvent être enregistrés à l'adresse https://pkgs.racket-lang.org/, ou peuvent être 
  installés directement depuis un dépôt Git, un website, un fichier ou un répertoire. Voir la page
  Package Management in Racket (anglais) pour plus d'informations.

* Pour sauver vos définitions, cliquez sur Sauver définitions dans le menu de DrRacket.

  Beaucoup de modules dépendent relativement d'autres modules, sans nécessairement appartenir à une collection de paquets en particulier. Par exemple, dans DrRacket, si vous sauvez vos définitions dans un fichier "quick.rkt" et ajoutez la ligne

```racket
> (provide rainbow square)
```

  alors vous pourrez ouvrir un nouvel onglet ou une nouvelle fenêtre dans DrRacket, nommez le nouveau programme "use.rkt" dans le même répertoire que "quick.rkt":

```racket
> \#lang racket
> (require "quick.rkt")
> (rainbow (square5))
```

et quand vous lancez "use.rkt", une liste arc-en-ciel de carrés est retournée. Notez que "use.rkt" est écrit en utilisant l'importation racket original, qui ne supporte pas les fonctions de création d'images mais fournis les fontions require et les fonctions d'appel de syntaxe.

  Les racketeurs écrivent typiquement des nouveaux programmes et librairies comme des modules qui s'importent les uns les autres via des chemins relatifs et des chemins basés sur les collections. Cela aide les autres utilisateures quand un programme ou une librairie sont développés de cette façon, il peut être enregistré comme paquet, en particulier si l'implémentation est hébergée dans un répertoire Git.
