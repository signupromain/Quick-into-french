## Définitions
Pour utiliser un ... cercle et une image de rectangle à chaque fois, il est plus simple d'envoyer leur noms. Revenez à la zone de définitions (la zone supérieure) et ajoutez deux définitions, de sorte que le contenu complet de la zone de définition ressemble à ceci: 

```racket
#lang slideshow
(define c (circle 10))
(define r (rectangle 10 20))
```
Puis cliquez sur Exécuter à nouveau. Maintenant, vous pouvez simplement taper c ou r :

```racket
> r
image

> (hc-append c r)
image

> (hc-append 20 c r c)
image
```

Comme vous pouvez le voir, la fonction ```hc-append``` accepte un argument optionnel number avant les arguments picture, et accepte un nombre quelconque d'arguments image. Lorsqu'un nombre est fourni, il spécifie la quantité d'espace à ajouter entre les images.

Nous aurions pu évaluer ```define``` des formes pour c et r dans la zone d'interactions au lieu de la zone de définitions. En pratique, cependant, la zone de définitions est l'endroit où vit votre programme - c'est le fichier que vous enregistrez - tandis que la zone d'interaction est destinée aux explorations transitoires et aux tâches de débogage.

Ajoutons une définition de fonction au programme. Une définition de fonction utilise ```define``` , tout comme nos définitions de forme, mais avec une parenthèse ouvrante avant le nom de la fonction, et des noms pour les arguments de la fonction avant la parenthèse fermante correspondante:

```racket
(define (square n)
  ; A semi-colon starts a line comment.
  ; The expression below is the function body.
  (filled-rectangle n n))
```

La syntaxe de la définition reflète la syntaxe d'un appel de fonction:

```racket
> (square 10)
image
```

De la même manière que les définitions peuvent être évaluées dans la zone des interactions, les expressions peuvent être incluses dans la zone des définitions. Lorsqu'un programme est exécuté, les résultats d'expression de la zone de définition sont affichés dans la zone d'interaction. À partir de maintenant, nous écrirons ensemble nos exemples de définitions et d'expressions, et vous pourrez les placer dans la zone que vous préférez. Les exemples se complètent cependant, il est donc préférable de mettre au moins les définitions dans la zone de définition.
