### exercice 4.1

Soit le programme Python suivant :

```python
def fct(n):
   if n > 5:
       return 1
   else :
       return n+fct(n+1)
a = fct(2)
```

Que vaut la variable a après l’exécution de ce programme (justifiez votre réponse) ?

### exercice 4.2

La fonction puissance prend un paramètre n et renvoie 2<sup>n</sup>. On définit la fonction puissance comme suit :

- si n = 0 alors puissance(0) = 1

- si n > 0 alors puissance(n) = 2 x puissance(n-1)

Écrivez en Python une version récursive de la fonction puissance

