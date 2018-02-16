## chapitre 8

racket hérite d'une grande partie de son style de la langue Lisp, dont le nom signifiait à l'origine "LISt Processsor" et les listes restent une partie importante de Racket.

La fonction  list prend n'importe quel nombre d'arguments et renvoie uen liste contenant les valeurs données:

>(liste "rouge" "vert" "bleu")
'("rouge" "vert" "bleu")
>(liste (cercle 10)(carré 10))

Comme vous pouvez le voir, une liste s'imprime sous la forme d'une simple citation, puis d'une paire de parenthèses entourant la forme imprimée des éléments de la liste. Ce qui peut porter à confusion, parce que les parenthèses sont utilisées pour les deux expressions, comme (cercle10) et les résultats imprimés, tels que ("trouge" "vert" "bleu").
La citation ets la clé differente clé, comme précisé avant.
Pour aider à souligner la difference, dans la documentation et dans DrRacket, les parenthèses de résultats sont impreimées en bleu, contrairement aux parenthèses d'expression. 

Si vous avez une liste, vous vous ferez quelque chose avec chacun des éléments. La map fonction  prend une liste et une fonction pour appliquer pour  
