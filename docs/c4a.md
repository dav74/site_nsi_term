### activité 4.1

On rappelle que la suite de Fibonacci est définie comme suit :

- u<sub>0</sub> = 0 et u<sub>1</sub> = 1

- et par la relation de récurrence suivante avec n entier et n > 1 : u<sub>n</sub> = u<sub>n-1</sub> + u<sub>n-2</sub>

 Écrivez une fonction récursive fib qui donnera le n ième terme de la suite de Fibonacci. Cette fonction prendra en paramètre l'entier n.

### activité 4.2

Dans cette activté, nous allons utiliser le module Python Turtle. Ce module permet de dessiner très simplement.

Étudiez le Wikibook consacré au module Turtle ([wikibook Turtle](https://fr.wikibooks.org/wiki/Programmation_Python/Turtle)) afin d'acquérir les bases de ce module.

Essayez de prévoir le résultat de l'exécution du programme ci-dessus. Vérifiez votre hypothèse en exécutant le programme.

```python
import turtle as t
t.forward(100)
t.left(120)
t.forward(100)
t.left(120)
t.forward(100)
```

Nous allons maintenant étudier le flocon de Koch.

Visionnez la vidéo consacrée au flocon de Koch : [vidéo consacrée au flocon de Koch](https://www.youtube.com/watch?v=PW_Pka9iBko&t=1s)

Après avoir testé le programme ci-dessous, vous l'étudierez attentivement. Vous vous concentrerez notamment sur le rôle des paramètres taille et etape de la fonction flocon.

```python
import turtle as t

def koch(longueur, n):
    if n == 0:
        t.forward(longueur)
    else:
        koch(longueur/3, n-1)
        t.left(60)
        koch(longueur/3, n-1)
        t.right(120)
        koch(longueur/3, n-1)
        t.left(60)
        koch(longueur/3, n-1)

def flocon(taille, etape):
    koch(taille, etape)
    t.right(120)
    koch(taille, etape)
    t.right(120)
    koch(taille, etape)

flocon(100, 3)
```

