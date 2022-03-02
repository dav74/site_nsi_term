Avant d'évoquer le projet en tant que tel, nous allons commencer par travailler sur les requêtes SQL effectuées depuis un programme Python. Il est donc nécessaire de bien maitriser toute la partie consacrée aux bases de données et particulièrement le cours sur les requêtes SQL

### projet 1.1

Après avoir créé un répertoire "projet_bd". Créez, à l'aide de spyder, un fichier Python (à vous de choisir le nom) puis saisissez et exécutez le programme suivant :

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

cur.execute("CREATE TABLE LIVRES(id INT, titre TEXT, auteur TXT, ann_publi INT, note INT)")

conn.commit()

cur.close()
conn.close()
```

Analysons le programme ci-dessus :

Ce programme va vous permettre de vous "connecter" à une base de données (si cette dernière n'existe pas, elle sera créée). Ensuite nous créons une table (une relation) nommée LIVRES, cette table contient 4 attributs : id (de type entier), titre (de type texte), auteur (de type texte), ann_publi (de type entier) et note (de type entier).

Entrons un peu dans les détails en analysant le programme ligne par ligne :

```
import sqlite3
```

Nous commençons par importer la bibliothèque sqlite3. Cette bibliothèque va nous permettre d'effectuer des requêtes SQL sur une base de données. Comme dans le cours sur les bases de données, nous utiliserons le SGBD SQLite.

```
conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()
```

Nous créons un objet de type "connection" (conn) qui va nous permettre d'interagir avec la base de données "baseDonnees.db" (comme dit plus haut, si cette base de données n'existe pas, elle est créée). Vous devriez donc avoir un fichier "baseDonnees.db" dans le même répertoire que votre fichier Python.

Nous créons ensuite un objet de type "cursor" à partir de l'objet de type "connection". Cet objet de type "cursor" va nous permettre de manipuler la base de données et d'obtenir des résultats lorsque nous effectuerons des requêtes.

```
cur.execute("CREATE TABLE LIVRES(id INT, titre TEXT, auteur TXT, ann_publi INT, note INT)")
```

La méthode "execute" de notre objet de type "cursor" nous permet d'effectuer une requête SQL. Cette requête SQL est en tout point identique à ce que nous avons vu dans le cours sur les bases de données.

```
conn.commit()
```

Pour véritablement exécuter les requêtes, il est nécessaire d'appliquer la méthode "commit" à l'objet de type "connection".

```
cur.close()
conn.close()
```

Avant de terminer le programme, il nécessaire de "fermer" l'objet de type "cursor" et l'objet de type "connection".

Nous allons systématiquement retrouver cette structure dans nos futurs programmes :

- création d'un objet de type "connection"
- création d'un objet de type "cursor"
- préparation d'une ou plusieurs requête(s) (méthode "execute" sur l'objet de type "cursor")
- exécution réelle des requêtes (méthode "commit" sur l'objet de type "connection")
- "fermeture" de l'objet de type "cursor" puis de l'objet de type "connection"

Si vous exécutez une deuxième fois le programme proposé au "À faire vous-même 1", vous aurez droit à une erreur : "OperationalError: table LIVRES already exists". Afin d'éviter ce genre de problème, il est possible de modifier le programme afin que la requête de création de la table LIVRES ne se fasse pas si la table LIVRES existe déjà :

### projet 1.2

Après avoir effacé le fichier "baseDonnees.db", saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

cur.execute("CREATE TABLE IF NOT EXISTS LIVRES(id INT, titre TEXT, auteur TXT, ann_publi INT, note INT)")

conn.commit()

cur.close()
conn.close()
```

Comme vous pouvez le constater, si vous exécutez le programme plusieurs fois de suite, il n'y a plus d'erreur.

### projet 1.3

Ouvrez le fichier "baseDonnees.db" à l'aide du logiciel "DB Browser for SQLite" et vérifiez que la table LIVRES a bien été créée.

Maintenant que notre table LIVRES a été créée, nous allons pouvoir commencer à la "remplir" avec des données :

### projet 1.4

Saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

cur.execute("CREATE TABLE IF NOT EXISTS LIVRES(id INT, titre TEXT, auteur TXT, ann_publi INT, note INT)")
cur.execute("INSERT INTO LIVRES(id,titre,auteur,ann_publi,note) VALUES(1,'1984','Orwell',1949,10)")

conn.commit()
```

Rien de particulier à signaler, la requête INSERT est identique à ce qui a été vu dans le cours sur les bases de données.

### projet 1.5

Ouvrez le fichier "baseDonnees.db" à l'aide du logiciel "DB Browser for SQLite" et vérifiez que les données ont bien été ajoutées à la table LIVRES.

Nous avons inclus les données à insérer directement dans la requête. Il est possible de procéder autrement en séparant les données à insérer et la requête (cela s'avérera particulièrement pratique dans le futur)

### projet 1.6

Après avoir effacé le fichier "baseDonnees.db", saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

data = (1,'1984','Orwell',1949,10)

cur.execute("CREATE TABLE IF NOT EXISTS LIVRES(id INT, titre TEXT, auteur TXT, ann_publi INT, note INT)")
cur.execute("INSERT INTO LIVRES(id,titre,auteur,ann_publi,note) VALUES(?, ?, ?, ?, ?)", data)
conn.commit()

cur.close()
conn.close()
```

Première chose à remarquer, nous avons créé un tuple (data) contenant toutes les informations. En effet, la méthode "execute" peut prendre un deuxième paramètre un tuple contenant les données à insérer. Les points d'interrogation présents dans la requête indiquent l'emplacement des données à insérer. Le premier ? sera remplacé par le premier élément du tuple (dans notre cas 1), le deuxième ? sera remplacé par le deuxième élément du tuple (dans notre cas '1984') et ainsi de suite...

Si l'on désire insérer plusieurs données, il est possible de regrouper toutes les données à insérer dans un tableau et d'utiliser la méthode "executemany" à la place de la méthode "execute".

### projet 1.7

Après avoir effacé le fichier "baseDonnees.db", saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

datas = [
	(1,'1984','Orwell',1949,10),
	(2,'Dune','Herbert',1965,8),
	(3,'Fondation','Asimov',1951,9),
	(4,'Le meilleur des mondes','Huxley',1931,7),
	(5,'Fahrenheit 451','Bradbury',1953,7),
	(6,'Ubik','K.Dick',1969,9),
	(7,'Chroniques martiennes','Bradbury',1950,8),
	(8,'La nuit des temps','Barjavel',1968,7),
	(9,'Blade Runner','K.Dick',1968,8),
	(10,'Les Robots','Asimov',1950,9),
	(11,'La Planète des singes','Boulle',1963,8),
	(12,'Ravage','Barjavel',1943,8),
	(13,'Le Maître du Haut Château','K.Dick',1962,8),
	(14,'Le monde des Ā','Van Vogt',1945,7),
	(15,'La Fin de l’éternité','Asimov',1955,8),
	(16,'De la Terre à la Lune','Verne',1865,10)
 ]

cur.execute("CREATE TABLE IF NOT EXISTS LIVRES(id INT, titre TEXT, auteur TXT, ann_publi INT, note INT)")
cur.executemany("INSERT INTO LIVRES(id,titre,auteur,ann_publi,note) VALUES(?, ?, ?, ?, ?)", datas)
conn.commit()

cur.close()
conn.close()
```

### projet 1.8

Ouvrez le fichier "baseDonnees.db" à l'aide du logiciel "DB Browser for SQLite" et vérifiez que les données ont bien été ajoutées à la table LIVRES.

Il n'est pas très pratique d'avoir à gérer l'id (clé primaire). En effet, si je veux ajouter un nouveau livre, il faudra que je connaisse l'id du précédent (incrémentation de l'id). Heureusement, il est possible d'automatiser cette incrémentation.

### projet 1.9

Après avoir effacé le fichier "baseDonnees.db", saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

datas = [
	('1984','Orwell',1949,10),
	('Dune','Herbert',1965,8),
	('Fondation','Asimov',1951,9),
	('Le meilleur des mondes','Huxley',1931,7),
	('Fahrenheit 451','Bradbury',1953,7),
	('Ubik','K.Dick',1969,9),
	('Chroniques martiennes','Bradbury',1950,8),
	('La nuit des temps','Barjavel',1968,7),
	('Blade Runner','K.Dick',1968,8),
	('Les Robots','Asimov',1950,9),
	('La Planète des singes','Boulle',1963,8),
	('Ravage','Barjavel',1943,8),
	('Le Maître du Haut Château','K.Dick',1962,8),
	('Le monde des Ā','Van Vogt',1945,7),
	('La Fin de l’éternité','Asimov',1955,8),
	('De la Terre à la Lune','Verne',1865,10)
 ]

cur.execute("CREATE TABLE IF NOT EXISTS LIVRES(id INTEGER PRIMARY KEY AUTOINCREMENT UNIQUE, titre TEXT, auteur TXT, ann_publi INT, note INT)")
cur.executemany("INSERT INTO LIVRES(titre,auteur,ann_publi,note) VALUES(?, ?, ?, ?)", datas)
conn.commit()

cur.close()
conn.close()
```

Ouvrez le fichier "baseDonnees.db" à l'aide du logiciel "DB Browser for SQLite" et vérifiez que les données ont bien été ajoutées à la table LIVRES.

Vous pouvez constater que nous avons bien l'attribut "id", même si ce dernier n'a pas été renseigné dans les données (absence d'id dans le tableau datas). Désormais l'id sera incrémenté automatiquement grâce au "id INTEGER PRIMARY KEY AUTOINCREMENT UNIQUE" (attention il est nécessaire d'utiliser INTEGER à la place du INT habituel) présent dans la requête de création de la table LIVRES. Attention, de bien penser à supprimer un ? dans la requête d'insertion (chaque tuple contient maintenant 4 éléments (nous en avions 5 quand l'id n'était pas géré automatiquement)).

Il est tout à fait possible de rajouter une nouvelle donnée :

### projet 1.10

Saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()
nvx_data = ('Hypérion','Simmons',1989,8)

cur.execute("INSERT INTO LIVRES(titre,auteur,ann_publi,note) VALUES(?, ?, ?, ?)", nvx_data)
conn.commit()

cur.close()
conn.close()
```

Ouvrez le fichier "baseDonnees.db" à l'aide du logiciel "DB Browser for SQLite" et vérifiez que les données ont bien été ajoutées à la table LIVRES.

Vous pouvez remarquer que le nouvel enregistrement a bien l'id 17 et que nous n'avons pas eu à nous en occuper.

Il est possible de modifier des données déjà présentes dans la table.

### projet 1.11

Saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

modif = (7, 'Hypérion')
cur.execute('UPDATE LIVRES SET note = ? WHERE titre = ?', modif)
conn.commit()

cur.close()
conn.close()
```

Ouvrez le fichier "baseDonnees.db" à l'aide du logiciel "DB Browser for SQLite" et vérifiez que les données ont bien été modifiées dans la table LIVRES.

Comme vous pouvez le constater, il est possible d'utiliser la clause WHERE avec un ?

Il est aussi possible de supprimer une donnée :

### projet 1.12

Saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

suppr = ('Hypérion',)
cur.execute('DELETE FROM LIVRES WHERE titre = ?', suppr)
conn.commit()

cur.close()
conn.close()
```

Ouvrez le fichier "baseDonnees.db" à l'aide du logiciel "DB Browser for SQLite" et vérifiez que l'entrée "Hypérion" a été supprimée de la table LIVRES.

Attention, le deuxième paramètre de la méthode "execute" doit être un tuple, si on écrit seulement suppr = ('Hypérion'), suppr est une chaine de caractère et pas un tuple. Pour avoir un tuple avec un seul élément il est nécessaire d'ajouter une virgule (d'où le suppr = ('Hypérion',))

Enfin, pour terminer cette introduction sur l'utilisation de sqlite en Python, nous devons nous intéresser aux requêtes de type "SELECT" :

### projet 1.13

Saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

cur.execute('SELECT * FROM LIVRES')
conn.commit()

liste = cur.fetchall()

cur.close()
conn.close()
```

À l'aide de la console, déterminez la valeur référencée par la variable liste

Comme vous pouvez le constater, la variable liste est un tableau qui contient des tuples. Chaque tuple est un enregistrement de la table LIVRES. La méthode "fetchall" d'un objet de type "cursor" renvoie un tableau contenant des tuples

Il est possible d'avoir des requêtes plus sélectives :

### projet 1.14

Saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

cur.execute('SELECT titre FROM LIVRES WHERE ann_publi < 1970')
conn.commit()

liste = cur.fetchall()
```

À l'aide de la console, déterminez la valeur référencée par la variable liste

Vous pouvez constater que l'on obtient bien un tableau contenant des tuples (nous avons bien des tuples même si seuls les titres ont été sélectionnés)

Il est possible d'utiliser les points d'interrogation dans une requête de type SELECT :

### projet 1.15

Saisissez le programme ci-dessous, puis exécutez-le

```
import sqlite3

conn = sqlite3.connect('baseDonnees.db')
cur = conn.cursor()

recherche = (1960, 8)

cur.execute('SELECT titre FROM LIVRES WHERE ann_publi < ? AND note > ?', recherche)
conn.commit()

liste = cur.fetchall()

cur.close()
conn.close()
```

À l'aide de la console, déterminez la valeur référencée par la variable liste

### projet 1.16

Vous allez maintenant reprendre le projet étudié l'année dernière : [Projet répertoire téléphonique version web](https://pixees.fr/informatiquelycee/n_site/nsi_prem_projet_4.html)

Cette année, au lieu d'utiliser un fichier texte pour stocker les noms et les numéros téléphone, il vous faudra utiliser une base de données (SGBD SQLite)

À part cela, aucun autre changement n'est attendu (on utilisera toujours Flask)

Pour rappel, voici la vidéo qui vous montre votre objectif : [vidéo projet répertoire téléphonique version web](https://www.youtube.com/watch?v=xTETvikDMBw&t=1s)


