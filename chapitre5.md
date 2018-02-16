## 5. Liaison locale
La forme ```racket define``` peut-être utilisée dans certaines situations pour créer des liaisons locales. Par exemple, elle peut être utilisée à l'intérieur d'une fonction principale:

```racket
(define(four p))
(define two-p (hc-append p p))
(vc-append two-p two-p))

> (four(circle 10))

```

Plus typiquement, les Racketeurs utilisent la forme  ```racket let``` ou ```racket let*```  pour créer une liaison locale. Un avantage de ```racket let``` est qu'il peut être utilisé n'importe où à l'intérieur d'une expression. De plus, il relie plusieurs identifiants à la fois, au lieu de nécessiter  une ```racket define```  séparée pour chaque identifiant: 

```racket

(define)(checker p1 p2)
(let [p12 (hc-append p1 p2)]
    [p21 (hc-append p2 p1)])
(vc-append p12 p21)))

> (checker (colorize (square 10) "red")
        (colorize (square 10) "black"))
```
Une forme ```racket let``` relie plusieurs idetifiants en même temps, de manière à ce que les liaisons ne
puissent pas se reférer entre elles. La forme ```racket let*```, a contrario, permet d'utiliser dans les liaisons suivantes, définies au préalable.

```racket
(define (checkerboard p)
  (let* ([rp (colorize p "red")]
         [bp (colorize p "black")]
         [c (checker rp bp)]
         [c4 (four c)])
    (four c4)))
 

> (checkerboard (square 10))
```
