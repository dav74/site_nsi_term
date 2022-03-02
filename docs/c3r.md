### Ce qu’il faut savoir

- Pour consulter des données, ajouter une entrée, modifier une entrée ou supprimer
  une entrée dans une base de données relationnelle, il est nécessaire d’effectuer des “requêtes SQL” (utilisation du langage SQL)

- Pour ajouter des entrées à une table, on utilisera “INSERT” (exemple : INSERT INTO LIVRES
  (id,titre,auteur,ann_publi,note) VALUES (1,'1984','Orwell',1949,10);)

- Pour interroger une table, on utilisera “SELECT” (exemple : SELECT titre FROM
  LIVRES WHERE auteur='Asimov')

- Pour modifier une entrée, on utilisera “UPDATE” (exemple : UPDATE LIVRES SET
  note=7 WHERE titre = 'Hypérion')

- Pour supprimer une entrée, on utilisera “DELETE” (exemple : DELETE FROM
  LIVRES WHERE titre='Hypérion')

- Pour réaliser une jointure, il est possible d’utiliser “INNER JOIN” (exemple : SELECT FROM LIVRES INNER JOIN AUTEURS ON LIVRES.id_auteur = AUTEURS.id)

### Ce qu’il faut savoir faire

- Vous devez être capable d’effectuer des requêtes SQL simples (utilisation de
  “INSERT”, “SELECT”, “UPDATE” et “DELETE”)

- Vous devez être capable d’effectuer une jointure entre 2 tables (utilisation de “INNER JOIN”)

