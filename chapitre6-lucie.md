#Les fonctions sont des valeurs
Plutôt que de considérer ‘circle’ comme un fonction, essayez de
l’envisager comme une expression.

> circle
#<procedure:circle>

C’est à dire que l’identifiant ‘circle’ est lié à la fonction (aka la procédure), tout comme
‘c’ est lié au cercle. Contrairement à la représentation d’un cercle, il n’y pas de façon
simple d’afficher complètement la fonction donc Dr Racket affiche #<procedure:circle>.


Cet exemple démontre que les fonctions sont des valeurs, tout comme les nombres
et les images (même si elles ne s'affichent pas aussi bien). Les fonctions étant
des valeurs, vous êtes en mesure de définir des fonctions qui acceptent d'autres
fonctions comme arguments.

(define (series mk)
(hc-append 4 (mk 5) (mk 10) (mk 20)))

```racket
> (series circle)

> (serie square)
```
Quand une fonction qui appelle une fonction comme argument est appelée,
la fonction argument n'est souvent nécessaire null part ailleurs. Devoir écrire la
fonction via 'define' serait problématique puisque vous devez la nommer et
trouver un endroit où la définir. La solution alternative est de créer
lambda qui créera une fonction anonyme :

> (series (lamba (size) (checkerboard (square size))))

Les noms entre parenthèses après 'lambda' sont les arguments de la fonction
et l'expression après l'argument est le corps de la fonction. Utiliser le mot 'lambda'
plutôt que 'fonction' ou 'procédure' fait partie intégrante de l'histoire et la 
culture de Racket.

La plupart des Racketeers préfèrent utiliser la forme raccourcie de la fonction
avec 'define' plutôt que de l'étendre à 'lambda'.
