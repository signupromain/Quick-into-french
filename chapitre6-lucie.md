Les fonctions sont des valeurs
Plutôt que de considérer ‘circle’ comme un fonction, essayez de
l’envisager comme une expression.
> circle
#<procedure:circle>
C’est à dire que l’identifiant ‘circle’ est lié à la fonction (aka la procédure), tout comme
‘c’ est lié au cercle. Contrairement à la représentation d’un cercle, il n’y pas de façon
simple d’afficher complètement la fonction donc Dr Racket affiche
#<procedure:circle>.

Cet exemple démontre que les fonctions sont des valeurs, tout comme les nombres
et les images (même si elles ne s'affichent pas aussi bien). Les fonctions étant
des valeurs, vous êtes en mesure de définir des fonctions qui acceptent d'autres
fonctions comme arguments.

