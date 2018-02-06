11 Objets


Un système objet est un autre exemple d'extension de langage sophistiqué qui vaut la peine d'être appris
et utilisé par les utilisateurs de Racket.
Les objets sont parfois meilleurs que les fonctions,
même lorsque vous avez lambda,
et les objets fonctionnent particulièrement bien pour les interfaces utilisateur graphiques.
L'API de l'interface graphique et du système graphique de Racket
est exprimée en termes d'objets et de classes.

Le système de classe est lui-même est implémenté par la bibliothèque racket / class,
et la bibliothèque racket / gui / base fournit les classes de GUI et de dessin.
Par convention, les classes reçoivent des noms qui se terminent par%:

```racket

    (require racket/class
         racket/gui/base)
(define f (new frame% [label "My Art"]
                      [width 299]
                      [height 299]
                      [alignment '(center center)]))

 
> (send f show #t)



```

La forme new crée une instance d'une classe, où les arguments d'initialisation
tels que label et width sont fournis par name.
Le formulaire d'envoi appelle une méthode de l'objet,
telle que show, avec des arguments après le nom de la méthode;
l'argument #t dans ce cas est la constante booléenne "true".

Les images générées avec un diaporama encapsulent une fonction qui utilise les commandes
de dessin de la boîte à outils graphique pour rendre
l'image dans un contexte de dessin, tel qu'un canevas dans un cadre.
La fonction make-pict-drawer du diaporama expose la fonction de dessind'une image.
Nous pouvons utiliser make-pict-drawer dans un callback de canvas-painting
pour dessiner une image dans une toile:

```racket





    (define (add-drawing p)
      (let ([drawer (make-pict-drawer p)])
        (new canvas% [parent f]
                     [style '(border)]
                     [paint-callback (lambda (self dc)
                                       (drawer dc 0 0))])))

    > (add-drawing (pict+code (circle 10)))

    #(struct:object:canvas% ...)
    > (add-drawing (colorize (filled-flash 50 30) "yellow"))

    #(struct:object:canvas% ...)
```

chaque "canvas" s'étire pour remplir une partie égale du cadre,
car c'est ainsi qu'un cadre gère ses enfants par défaut.
