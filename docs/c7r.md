### ce qu'il faut savoir

Les arbres sont des types abstraits très utilisés en informatique. On les utilise notamment
quand on a besoin d'une structure hiérarchique des données.

![](img/nsi_term_structDo_arbre_3.png)

Vocabulaire :

- chaque élément de l'arbre est appelé noeud (par exemple : A, B, C, D,...,P et Q sont des noeuds)
- le noeud initial (A) est appelé noeud racine ou plus simplement racine
- On dira que le noeud E et le noeud D sont les fils du noeud B. On dira que le noeud B est le père des noeuds E et D
- Dans un arbre binaire, un noeud possède au plus 2 fils
- Un noeud n'ayant aucun fils est appelé feuille (exemples : D, H, N, O, J, K, L, P et Q sont des feuilles)
- À chaque noeud d'un arbre binaire, on associe une clé ("valeur" associée au noeud on peut aussi utiliser le terme "valeur" à la place de clé), un "sous-arbre gauche" et un "sous-arbre droit" (exemple : à partir du noeud ayant pour clé C on va trouver un sous-arbre gauche composé des noeuds F, J et K et un sous-arbre droit composé des noeuds G, L, M, P et Q)
- Un arbre (ou un sous-arbre) vide est noté NIL (NIL est une abréviation du latin nihil qui veut dire "rien"). Par exemple, le sous-arbre gauche du noeud D est NIL (même chose pour son sous-arbre droit d'ailleurs puisque D est une feuille).
- On appelle arête le segment qui relie 2 noeuds.
- On appelle taille d'un arbre le nombre de noeuds présents dans cet arbre
- On appelle profondeur d'un nœud ou d'une feuille dans un arbre binaire le nombre de nœuds du chemin qui va de la racine à ce nœud. La racine d'un arbre est à une profondeur 1, et la profondeur d'un nœud est égale à la profondeur de son prédécesseur plus 1. Si un noeud est à une profondeur p, tous ses successeurs sont à une profondeur p+1. Exemples : profondeur de B = 2 ; profondeur de I = 4 ; profondeur de P = 5
ATTENTION : on trouve aussi dans certains livres la profondeur de la racine égale à 0 (on trouve alors : profondeur de B = 1 ; profondeur de I = 3 ; profondeur de P = 4). Les 2 définitions sont valables, il faut juste préciser si vous considérez que la profondeur de la racine est de 1 ou de 0.
- On appelle hauteur d'un arbre la profondeur maximale des nœuds de l'arbre. Exemple : la profondeur de P = 5, c'est un des noeuds les plus profond, donc la hauteur de l'arbre est de 5.
ATTENTION : comme on trouve 2 définitions pour la profondeur, on peut trouver 2 résultats différents pour la hauteur : si on considère la profondeur de la racine égale à 1, on aura bien une hauteur de 5, mais si l'on considère que la profondeur de la racine est de 0, on aura alors une hauteur de 4.

Pour un arbre binaire quelconque, nous avons :

$\lfloor log_2(n) \rfloor  \leq h \leq n-1$
				
avec n la taille de l'arbre et h la hauteur de l'arbre ($\lfloor log_2(n) \rfloor$ permet de prendre la partie entière du logarithme base 2 de n.

Il est aussi important de bien noter que l'on peut aussi voir les arbres comme des structures
récursives : les fils d'un nœud sont des arbres (sous-arbre gauche et un sous-arbre droite
dans le cas d'un arbre binaire), ces arbres sont eux-mêmes constitués d'arbres...

Un arbre binaire de recherche est un cas particulier d'arbre binaire. Pour avoir un arbre binaire de recherche :

- il faut avoir un arbre binaire
- il faut que les clés de noeuds composant l'arbre soient ordonnables (on doit pouvoir classer les noeuds, par exemple, de la plus petite clé à la plus grande)
- soit x un noeud d'un arbre binaire de recherche. Si y est un noeud du sous-arbre gauche de x, alors il faut que y.clé ⩽ x.clé. Si y est un noeud du sous-arbre droit de x, il faut alors que x.clé ⩽ y.clé

Attention : pour un noeud donné A, tous les noeuds de l'arbre gauche de A auront des valeurs plus petites que la valeur du noeud A et tous les noeuds de l'arbre droit de A auront des valeurs plus grandes que la valeur du noeud A. 
