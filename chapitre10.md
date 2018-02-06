 chapitre10

10.Des  macros
Voici une autre bibliothèque a essayer:
(require slideshow/code)

 
 > (code (circle 10))

 (circle10)
Au lieu d’un cercle, le résultat est une image du code qui, s’il était utilisé comme une expression, produirait un cercle.
En d’autres termes, le code n’est pas une fonction, mais plutôt une nouvelle forme syntaxique pour créer des
images; le bit entre les parenthèses ouvrantes avec le code n’est pas une expression, mais plutôt manipulé par la forme syntaxique du code.

Cela aide a expliquer ce que nous voulions dire dans la section précédente quand
nous avons dit que la raquette fournit réquire et la syntaxe d’appel de
fonction.
