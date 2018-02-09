# chapitre 8

Racket hérite d'une grande partie de son style de la langue Lisp, dont le nom signifiait à l'origine "LISt Processsor" et les listes restent une partie importante de Racket.

La fonction  list prend n'importe quel nombre d'arguments et renvoie une liste contenant les valeurs données:

>(liste "rouge" "vert" "bleu")
'("rouge" "vert" "bleu")
>(liste (cercle 10)(carré 10))

Comme vous pouvez le voir, une liste s'imprime sous la forme d'une simple citation, puis d'une paire de parenthèses entourant la forme imprimée des éléments de la liste. Ce qui peut porter à confusion, parce que les parenthèses sont utilisées pour les deux expressions, comme (cercle10) et les résultats imprimés, tels que ("rouge" "vert" "bleu").
La citation est la clé differente clé, comme précisé avant.
Pour aider à souligner la difference, dans la documentation et dans DrRacket, les parenthèses de résultats sont impreimées en bleu, contrairement aux parenthèses d'expression. 

Si vous avez une liste, vous vous ferez quelque chose avec chacun des éléments. La map fonction  prend une liste et une fonction pour s'appliquer à chaque élément de la liste.
 Il en fait une nouvelle pour combiner les résultats des fonctions.

Une autre fonction qui travaille avec des listes s'applique.
Comme la map, il prend une fonction et une liste, mais une fonction pour s'appliquer devrait prendre tous les arguments immédiatement.
L'application fonction est spécialement  utilisé avec les fonctions qui utilisent tous les numéros tels que vc-	append:

Notons que (vc (rainbow (square5))) ne fonctionne pas parceque vc-append n'ont pas besoin d'une branche tel un argument; il veut une image tel un argument, 
Et il est enclin d'accepter n'importe quel nombre d'entre eux.
La fonction s'applique comble le fossé entre une liste de tous les arguments telle une valeur seule.    
