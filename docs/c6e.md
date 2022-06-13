### exercice 6.1
Soit le programme Python suivant :
```python
inventaire = {'pommes': 430, 'bananes': 312,'oranges' : 274, 'poires' : 137}

stock = 0
for fruit in inventaire.keys():
  if fruit != 'bananes':
    stock = stock + inventaire[fruit]
```
Quelle est la valeur de la variable stock après l'exécution de ce programme ?

### exercice 6.2

Soit le programme Python suivant :

```python

P = [{"nom":"Turing","prenom":"Alan","age":28},{"nom":"Lovelace","prenom":"Ada","age":27}]
```
Qu'obtient-on si  on  tape P[1]['age'] dans une console Python  ?

### exercice 6.3

Soit le programme Python suivant :

```python
def ajoute(stock,element,quantite):
  if element in stock:
    stock[element] = stock[element] + quantite
  else:
    stock[element] = quantite

stock = { 'clous': 14, 'vis': 27, 'boulons': 8, 'écrous': 24 }
ajoute(stock,'vis',5)
ajoute(stock,'chevilles',3)
```
Quelle est la valeur de la variable stock à la fin de cette exécution ?

### exercices du bac

- [Sujet 6 2021 Exercice 2](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_6.pdf)
- [Sujet 10 2021 Exercice 2](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_10.pdf)
- [Sujet 6 2022 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_06.pdf)
- [Sujet 6 2022 Exercice 3](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_06.pdf)
- [Sujet 7 2022 Exercice 2](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_07.pdf)

