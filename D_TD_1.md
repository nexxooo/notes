---
attachments: [TD 1.md]
tags: [D1]
title: D TD 1
created: '2025-09-08T08:49:22.965Z'
modified: '2025-09-08T11:28:12.999Z'
---

#  D TD 1 

**interrogation:**
~~~ 
SELECT
~~~

## Requete simple

~~~sql
SELECT
FROM ;
~~~

> on peut renomer l'affichage avec :
~~~sql
SELECT ex"Nom"
FROM ;
~~~
>pour ne pas avoir de doublons :

~~~sql
SELECT DISTINCT
~~~

## RESTRICTION

~~~sql
SELECT
FROM
WHERE ;
~~~

## CONDITION
~~~sql
[NOT] IN
IS [NOT] NULL
[NOT] BETWEEN * and * 
[NOT] LIKE 
~~~
### Pour Like 
___

- **'S%'** = chaine commencant par S
- **'%s'** chaine terminant par s
- **'_a%'** chaine avec un 'a' en 2 position
- **' _ a___'** chaine avec un 'a' en 2e position et avec 5 caractère 
### BOLEEN
___
~~~sql
AND
NOT 
OR 
~~~

## TRIER

~~~sql
SELECT 
FROM
ORDER BY 
~~~
> ORDER BY est par defaut croissant pour decroissant (DESC)

## FONCTION

~~~sql
ABS(n)
CEIL(n) le plus petit entier > n
FLOOR(m,n) le plus grand entier < n
MOD(m,n) m[n]
POWER(m,n)
ROUND(n,m)
TRUNC(n,m)
SQRT(n)
LEAST(n,m) plus petit element 
GREATEST(n,m) plus grand element 
~~~
> AU moins une valeur de la liste satisfait la condition
~~~sql
ANY
~~~

> La condition est réalisée par toutes les valeurs de la liste
~~~sql
ALL
~~~
---
### en algèbre
pour afficher une ligne = proj, une colonne = res 

---

## DATE
* comparaison entre deux date (=,!=,<,...)
* date1 - date2 soustraction de deux dates qui retourne un réel
* date + constante: ajout d'un nombre de jours



## STR
concatener = ||
on peut aussi :
~~~sql
UPPER()
LOWER()
INITCAP()
~~~
### conversion
~~~sql
to_char()
to_date()
to_number()
~~~

## Requete avec jointure 
~~~sql
SELECT *
FROM pilotes
JOIN vols
ON vols.pilotes = pilotes.npilotes;
~~~
