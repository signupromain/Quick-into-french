 chapitre10

10.Des  macros
Voici une autre bibliothèque a essayer:
```(require slideshow/code)
 
 > (code (circle 10))

 (circle10)
 ```
Au lieu d’un cercle, le résultat est une image du code qui,
s’il était utilisé comme une expression, produirait un cercle.
En d’autres termes, ```code``` n’est pas une fonction,
mais plutôt une nouvelle forme syntaxique pour créer des
images; le bit entre les parenthèses ouvrantes avec ```code``` n’est pas une expression,
mais plutôt manipulé par la forme syntaxique du ```code```.

Cela aide a expliquer ce que nous voulions dire dans la section précédente quand
nous avons dit que  ```racket``` fournit ```require``` et la syntaxe d’appel de
fonction.

Les bibliothèques ne sont pas limitées à l'exportation de valeurs, telles que les fonctions;
ils peuvent également définir de nouvelles formes syntaxiques. En ce sens, Racket n'est pas du tout une langue;
c'est plus une idée de la façon de structurer un langage pour pouvoir l'étendre ou créer des langages entièrement nouveaux.

Une façon d'introduire une nouvelle forme syntaxique est de ```definie-syntaxe``` avec des ```syntax-rules```:
```(définir-syntaxe pict + code
      (règles de syntaxe ()
        [(pict + code expr)
         (hc-annexe 10
                    expr
                    (code expr))]))

     
    > (pict + code (cercle 10))

    (CIRCLE 10)
```
Ce genre de définition est une macro. La partie (pict + code expr) est un modèle pour les utilisations de la macro;
les instances du modèle dans un programme sont remplacées par des instances du modèle correspondant, qui est (```hc-append 10``` expr (```code``` expr)).
En particulier, (pict + code (```cercle 10```)) correspond au motif avec (```cercle 10```) comme expr, donc il est remplacé par (```hc-append 10 (cercle 10```) (```code (cercle 10)```)).

Bien sûr, ce genre d'extension syntaxique va dans les deux sens: inventer un nouveau langage peut rendre plus facile de dire ce que vous voulez,
mais plus difficile à comprendre pour les autres. En l'occurrence,
les développeurs de Racket donnent constamment des conférences et rédigent des articles qui impliquent le code Racket,
et cela vaut la peine pour tous ceux qui travaillent sur ces produits de connaître ```code```.

En fait, vous pouvez jeter un oeil à ```source of this document```.
Vous verrez que ça commence par #lang, mais ça ne ressemble pas beaucoup à Racket;
Néanmoins, nous construisons ce document en exécutant sa source en tant que programme Racket.
Nous devons utiliser beaucoup plus que des règles de syntaxe pour étendre suffisamment la syntaxe de Racket pour écrire des documents,
mais l'extension syntaxique de Racket peut vous prendre un long chemin.
