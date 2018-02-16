Portée lexicale

Racket est un langage à portée lexicale, ce qui signifie qu'à chaque fois qu'un identifiant est utilisé en tant qu'expression, quelque chose dans l'environnement textuel de l'expression détermine les liaisons de l'identifiant. Cet règle s'applique aux identifiant dans un corps ```lambda``` ainsi que partout ailleur.

Dans la fonction rgb-series suivante, les utilisations de mk dans chaque forme
```lambda``` font référence à l'argupment de rgb-series puisque c'est la liaison qui
est textuellement dans la portée:

```racket
(define (rgb-series mk)
  (vc-append
     (series (lambda (sz) (colorize (mk sz) "red")))
        (series (lambda (sz) (colorize (mk sz) "green")))
           (series (lambda (sz) (colorize (mk sz) "blue")))))

> (rgb-series circle)
> (rgb-series square)
```

Voici un autre exemple, où rgb-maker prend une focntion et renvoie une nouvelle
qui se souvient et utilise la fonction d'origine.
```racket
(define (rgb-maker mk)
(lambda (sz)
(vc-append (colorize (mk sz) "red")
(colorize (mk sz) "green")
(colorize (mk sz) "blue"))))
> (series (rgb-maker circle))
image
> (series (rgb-maker square))
image
```
Remarquez comment les fonctions de composition via rgb-maker créent un
alignement différent des objets dans l'image par rapport à l'utilisation de rgb-series.
