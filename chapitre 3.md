chapitre 3 

Quand tu tape une expression après le > dans la fenêtre 
d'intéraction et que tu tape la touche entrer, DrRacket évalue l'expression et affiche le résultat. Une expression peut juste avoir 
une valeur, comme le numéro 5 ou la chaine de caractère "art gallery":
```racket
  >5
 5
 > "art gallery"
 "art gallery"
 ```
 Une expression peut être aussi un appel de fonction. Pour appeler une fonction, ouvre des parenthèse avant le nom de la fonction,
 puis des expression pour les arguments de la fonction, et puis fermer les parenthèses, comme ceci:
 ```racket
 >(circle 10)
 o
 ```
 Le résultat de la fonction "circle" est une valeur d'image, qui affiche comme le résultat d'une expression, c'est la même chose
 pour l'affichage des numéros et chaines de caractère. L'argument de "circle" détermine la taille du cercle en pixels. Comme tu l'a
 deviné, la fonction "rectangle" utilise deux arguments au lieu d'un:
 
 >(rectangle 10 20)
 ▯
 
 Essaye d'entrer un mauvais argument à la fonction "circle" juste pour voir ce qu'il se passe:
 
 ```racket
  >(circle 10 20)
  circle: arity mismatch;
    Le nombre d'arguments attendu ne correspond pas au nombre donnée
    attendu: 1 plus des arguments optionnel accompagnée de mots clé
    #:couleur de la bordure et largeur de la bordure
    donner: 2 
    arugments...:
    10
    20
 ```
 Il faut noter que DrRacket met en surbrillance rose l'expression qui a declanché une erreur (mais la surbrillance rose n'est pas
 montré dans la documentation).
 
 Additionné a l'image construite de base comme le "circle" et "rectangle", la fonction "hc-happend" combiné a l'image. Quand tu 
 lance des appels de fonction dans Racket, ça se présente comme ca:
 
 ```racket
 > (hc-append (circle 10) (rectangle 10 20))
▯
o▯
 ```
 Le trait d'union dans le nom hc-append est juste une partie de l'identifiant, ce n'est pas hc moins append . 
 Le nom de la fonction commence par h parce qu'il combine les images horizontalement, et la lettre suivante 
 est "c" car les images sont centrées verticalement.

Si tu te demande quelles sont les autres fonctions qui existent - peut-être un moyen d'empiler verticalement 
les images et de les aligner à gauche? - déplacez le curseur de texte vers le nom hc-append et appuyez 
sur la touche F1 dans DrRacket. Une fenêtre du navigateur va s'ouvrir et vous donner un lien vers la 
documentation de hc-append . Cliquez sur le lien, et tu verra beaucoup d'autres fonctions.

Si tu lisez ceci au format HTML, tu peux également cliquer sur hc-append ou tout autre 
identifiant importé utilisé dans ce tutoriel.
