### exercice 5.1

Soit la suite d'instructions suivantes :

```
L = vide()
L = cons(2, cons(15, cons (23, L)))
L1 = cdr(L)
a = car(L1)
L1 = cons(4, cons(3, L1))
```
Donnez le contenu des listes L et L1 et la valeur de a.

### exercice 5.2

Soit une pile P initialement vide. Soit les instructions suivantes :

```
push(P,4)
push(P,7)
a = pop(P)
b = taille(P)
c = pop(P)
push(P,3)
push(P,2)
d = taille(P)
```
Donnez le contenu de la pile P, la valeur de a, la valeur de b, la valeur de c et la valeur de d.

### exercice 5.3

Soit une file F initialement vide. Soit les instructions suivantes :

```
enqueue(F,6)
enqueue(F,3)
a = dequeue(F)
enqueue(F,9)
b = taille(F)
enqueue(F,17)
c = dequeue(F)
enqueue(F,2)
d = taille(F)
```
Donnez le contenu de la file F, la valeur de a, la valeur de b, la valeur de c et la valeur de d.


### exercice 5.4

Soit le programme Python suivant :

```	
pile = []
tab = [5,8,6,1,3,7]
pile.append(5)
pile.append(10)
pile.append(8)
pile.append(15)
for i in tab:
    if i > 5:
        pile.pop()
```

Donnez l’état de la pile pile après l’exécution de ce programme.

### exercice 5.5

Soit le programme Python suivant :

```python
from collections import deque
file = deque([])
tab = [2,78,6,89,3,17]
file.append(5)
file.append(10)
file.append(8)
file.append(15)
for i in tab:
    if i > 50:
        file.popleft()
```

Donnez l’état de la file *file* après l’exécution de ce programme

### exercices du bac

- [Sujet 1 2021 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_1.pdf)
- [Sujet 3 2021 Exercice 5](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_3.pdf)
- [Sujet 6 2021 Exercice 5](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_6.pdf)
- [Sujet 7 2021 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_7.pdf)
- [Sujet 8 2021 Exercice 5](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_8.pdf)
- [Sujet 1 2022 Exercice 4](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_01.pdf)
- [Sujet 2 2022 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_02.pdf)
- [Sujet 3 2022 Exercice 2](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_03.pdf)
- [Sujet 4 2022 Exercice 5](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_04.pdf)
- [Sujet 10 2022 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_10.pdf)
- [Sujet 11 2022 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_11.pdf)
- [Sujet 14 2022 Exercice 5](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_14.pdf)


