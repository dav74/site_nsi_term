### exercice 6.1
Soit le programme Python suivant :
```
inventaire = {'pommes': 430, 'bananes': 312,'oranges' : 274, 'poires' : 137}

stock = 0
for fruit in inventaire.keys():
  if fruit != 'bananes':
    stock = stock + inventaire[fruit]
```
Quelle est la valeur de la variable stock après l'exécution de ce programme ?

### exercice 6.2

Soit le programme Python suivant :

```

P = [{"nom":"Turing","prenom":"Alan","age":28},{"nom":"Lovelace","prenom":"Ada","age":27}]
```
Qu'obtient-on si  on  tape P[1]['age'] dans une console Python  ?

### exercice 6.3

Soit le programme Python suivant :

```
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