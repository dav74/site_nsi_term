### activité 5.1

Soit la suite d'instructions suivantes :

```
L = vide()
L = cons(12, cons(5, cons (32, L)))
a = car(L)
L1 = cdr(L)
L1 = cons(42, cons(23, L1))
```
Donnez le contenu des listes L et L1 et la valeur de a.

### activité 5.2

Soit une pile P composée des éléments suivants : 15, 11, 32, 45 et 67 (le sommet de la pile est 67). Quel est l'effet de l'instruction pop(P) ?

### activité 5.3

Soit une pile P initialement vide. Soit les instructions suivantes :

```
push(P,34)
push(P,76)
push(P,43)
a = pop(P)
push(P,42)
b = taille(P) 
```
Donnez le contenu de la pile P, la valeur de a et la valeur de b.

### activité 5.4
Soit une file F composée des éléments suivants : 1, 12, 24, 17, 21 et 72 (le premier élément rentré dans la file est 72 ; le dernier élément rentré dans la file est 1). Quel est l'effet de l'instruction enqueue(F,25) ?

### activité 5.5

Soit une file F initialement vide. Soit les instructions suivantes :

```
enqueue(F,67)
enqueue(F,34)
enqueue(F,78)
a = dequeue(F)
enqueue(F,23)
b = taille(F)
```
Donnez le contenu de la file F, la valeur de a et la valeur de b.

### activité 5.6

Soit le programme Python suivant :

```python
def vide():
    return None
def estVide(L):
    return L is None
def cons(x,L):
    return (x,L)
def car(L):
    return(L[0])
def cdr(L):
    return(L[1])
```
Quel est le but de ce programme ? Vérifiez à l'aide de ce programme que les réponses que vous avez apportées à l'activité 5.1 étaient correctes.

### activité 5.7
Python propose une implémentation des piles. Après avoir étudié la documentation consacrée à l'implémentation des piles en Python (voir [https://docs.python.org/fr/3/tutorial/datastructures.html](https://docs.python.org/fr/3/tutorial/datastructures.html#using-lists-as-stacks) partie 5.1.1), vous écrirez un programme permettant de vérifier que les réponses que vous avez apportées à l'activité 5.3 étaient correctes.

### activité 5.8
Python propose une implémentation des files. Après avoir étudié la documentation consacrée à l'implémentation des files en Python (voir [https://docs.python.org/fr/3/tutorial/datastructures.html](https://docs.python.org/fr/3/tutorial/datastructures.html#using-lists-as-queues) partie 5.1.2), vous écrirez un programme permettant de vérifier que les réponses que vous avez apportées à l'activité 5.5 étaient correctes.

### activité 5.9
Écrivez une fonction Python permettant de déterminer le nombre d'éléments présents dans une liste.

