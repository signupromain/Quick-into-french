8 Lists

Racket hérite d'une grande partie de son style de la langue Lisp, dont le nom signifiait à l'origine "LISt Processsor" et les listes restent une partie importante de Racket.

La fonction ```list``` prend n'importe quel nombre d'arguments et renvoie une liste contenant les valeurs données:

```racket
> (list "red" "green" "blue")
'("red" "green" "blue")
> (list (circle 10) (square 10))
```

Comme vous pouvez le voir, une liste s'imprime sous la forme d'une simple citation, puis d'une paire de parenthèses entourant la forme imprimée des éléments de la liste. Ce qui peut porter à confusion, parce que les parenthèses sont utilisées pour les deux expressions, comme ```(circle 10) ``` et les résultats affichés, tels que ```("red" "green" "blue")```.
La citation est la différente clé, comme ```précisé avant```. Pour aider à mettre en évidence la différence, dans la documentation et dans DrRacket, les résultats entre les parenthèses sont signalés en bleu, contrairement aux parenthèses d'expression. 

Si vous avez une liste, vous ferez quelque chose avec chacun des éléments. La fonction ``` map``` prend une liste et une fonction pour s'appliquer à chaque élément de la liste. Elle renvoit à une nouvelle liste pour combiner les résultats des fonctions.

```racket
(define (rainbow p)
(map (lambda (color)
(colorize p color))
(list "red" "orange" "yellow" "green" "blue" "purple")))
 > (rainbow (square 5))
```

Une autre fonction qui marche avec des listes est ```apply```. Comme ```map```, elle prends une fonction et une liste, mais une fonction attribuée à ```apply``` poura prendre tous les arguments immédiatement. La fonction ```apply``` est spécialement utilisé avec des fonctions qui utilisent plusieurs arguments tels que ```vc-append```:

```racket
> (apply vc-append (rainbow (square 5)))
```

Notez que ```(vc (rainbow (square5)))``` ne fonctionnera pas, parce que ```vc-append``` ne veut pas une liste comme un argument; elle veut une image comme un argument, et elle est prête à accepter un certain nombre d'entre eux.
La fonction ```apply``` comble le fossé entre une liste de tous les arguments comme une valeur seule.    
