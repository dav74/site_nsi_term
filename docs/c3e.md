### exercice 3.1

Un ski-club utilise une base de données constituée de 2 tables :

- une table ADHERENTS
- une table STATIONS 

Dans la table ADHERENTS  on trouve un attribut “ref_station” qui permet de connaître les stations de ski préférées des adhérents.

Table ADHERENTS

| num_licence | nom    | prenom  | annee_naissance | ref_station |
| ----------- | ------ | ------- | --------------- | ----------- |
| 12558       | Doe    | John    | 1988            | 5           |
| 13668       | Vect   | Alice   | 1974            | 6           |
| 1777        | Dect   | Bob     | 1967            | 3           |
| 13447       | Beau   | Tristan | 1999            | 4           |
| 1141        | Pabeau | John    | 1975            | 3           |

table STATIONS

| ref | nom              | altitude_max |
| --- | ---------------- | ------------ |
| 3   | Le grand Bornand | 2050         |
| 4   | La clusaz        | 2616         |
| 5   | Flaine           | 2510         |
| 6   | Avoriaz          | 2466         |

1. Comment appelle-t-on l’attribut ref_station de la table ADHERENTS ?
2. Écrire la requête SQL permettant d’obtenir le nom des stations ayant une altitude maxi strictement supérieure à 2500 m.
3. Écrire une requête SQL permettant d’obtenir le numéro de licence des adhérents nés après 1980 et ayant pour prénom John.
4. Donnez le résultat de la requête SQL suivante :

```sql
SELECT nom 
FROM ADHERENTS 
WHERE num_licence > 2000 OR  ref_station = 3
```
5. Donnez le résultat de la requête SQL suivante :

```sql
SELECT STATIONS.nom
FROM STATIONS
INNER JOIN ADHERENTS ON ADHERENTS.ref_station = STATIONS.ref
WHERE annee_naissance > 1975
```

### exercices du bac

- [Sujet 1 2021 Exercice 4](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_1.pdf)
- [Sujet 2 2021 Exercice 3](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_2.pdf)
- [Sujet 3 2021 Exercice 2](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_3.pdf)
- [Sujet 4 2021 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_4.pdf)
- [Sujet 5 2021 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_5.pdf)
- [Sujet 7 2021 Exercice 4](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_7.pdf)
- [Sujet 8 2021 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_8.pdf)
- [Sujet 10 2021 Exercice 3](https://pixees.fr/informatiquelycee/term/suj_bac/2021/sujet_10.pdf)
- [Sujet 1 2022 Exercice 3](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_01.pdf)
- [Sujet 2 2022 Exercice 2](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_02.pdf)
- [Sujet 3 2022 Exercice 4](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_03.pdf)
- [Sujet 4 2022 Exercice 1](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_04.pdf)
- [Sujet 5 2022 Exercice 3](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_05.pdf)
- [Sujet 6 2022 Exercice 4](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_06.pdf)
- [Sujet 7 2022 Exercice 3](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_07.pdf)
- [Sujet 8 2022 Exercice 2](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_08.pdf)
- [Sujet 9 2022 Exercice 4](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_09.pdf)
- [Sujet 10 2022 Exercice 3](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_10.pdf)
- [Sujet 11 2022 Exercice 2](https://pixees.fr/informatiquelycee/term/suj_bac/2022/sujet_11.pdf)


