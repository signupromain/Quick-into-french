## Les fonctions sont des valeurs
5. Liaison locale
La forme définie peut-être utilisée dans quelque situation pour créer des liaisons locales. Par exemple, cela peut-être utilisé à l'intérieur d'une fonction principale:

```racket
(define(four p))
(define two-p (hc-append p p))
(vc-append two-p two-p))

> (four(circle 10))

```

PLus typiquement, les Racketers utilisent le let ou let forme pour liaison locale. Un avantage de let est qu'il peut être utilisé pour des éléments d'expression. Aussi, ça relie plusieurs identifiants en une seule fois, à la place de demander une requête séparée pour chaque identifiant: 

```racket

(define)(checker p1 p2)
(let [p12 (hc-append p1 p2)]
    [p21 (hc-append p2 p1)])
(vc-append p12 p21)))

> (checke(colorize(square 10)"red")
        (colorize(square 10)"black"))
```
Une forme let relie plusieurs idetifiants en même temps, alors les liaisons ne
peuvent pas se reférer entre elles. La forme let, en contraste, permets  plus
tard des liaisons à utiliser
