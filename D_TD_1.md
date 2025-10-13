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
## gerer des table 
### contrainte
- reférence 
- intégrité 
- applicative (ex arrivee != depart )
### Type 
~~~slq
char(n) 
varchar(n)
number
number(p)
number(p,d)
date 
~~~
### crée table 
~~~sql
CREATE TABLE nom
CONSTRAINT id PRIMARY KEY
CONSTRAINT fk FOREIGN KEY
REFERENCES dept(deptno) ON DELETE CASCADE
~~~
### convention
* pk_ cle primaire
* fk_ cle etrangere

### exemple
~~~sql 
CREATE TABLE emp
(empno number(8) NOT NULL, ename varchar2(20) NOT NULL,
job varchar2(20) NOT NULL, mgr number(8),
hiredate date DEFAULT sysdate,
sal number(8,2) NOT NULL, comm number(8),
deptno number(2),
CONSTRAINT c_emp_sal
CHECK(sal between 800 and 50000),
CONSTRAINT c_emp_commJob
CHECK((comm is not null and initcap(job) = 'Salesman') or
(comm is null and initcap(job) != 'Salesman') ),
CONSTRAINT u_emp_ename UNIQUE(ename),
CONSTRAINT pk_emp PRIMARY KEY (empno),
CONSTRAINT fk_emp_deptno FOREIGN KEY (deptno)
REFERENCES dept ON DELETE CASCADE,
CONSTRAINT fk_emp_mgr FOREIGN KEY (mgr)
REFERENCES emp
) ;
~~~
### supprimer
~~~
drop table ex
~~~
### renomer
~~~ 
remane ex to ex1
~~~
### modifier la table 
~~~sql
alter table emp
modify (sal number(10,2),job varchar2(30));

alter table emp
modify (job null) ;

alter table dept
add (budget number(6));

alter table dept
drop column budget ;
~~~
## VUE
### exemple
~~~sql
create view personnel
as select e.empno, e.ename, e.job,
d.dname, d.loc
from emp e JOIN dept d
ON e.deptno = d.deptno ;
~~~
permet de crée de table "fantome" pour les réutiliser sans tous réecrire
## MISE A JOUR 
### inseret 
~~~sql
INSERT INTO dept (deptno, dname, loc)
VALUES (55, 'LOISIR', 'STRASBOURG');
~~~
~~~sql
INSERT INTO chefs (no_chef, nom_chef)
SELECT empno, ename FROM emp
WHERE empno IN (SELECT mgr FROM emp);
~~~
~~~sql
INSERT INTO mondept (deptno, dname, loc)
VALUES (&numero, '&nom', '&ville');
~~~
> & pour demander les valeur 
### supprimer
~~~sql
DELETE 
FROM ex
WHERE ___
~~~
### modifier
~~~sql
UPDATE dept SET loc = 'PARIS';
WHERE ___
~~~
> update ne doit renvoyer qu'une seule valeur
## VALIDATION / ANNULATION
~~~sql
COMMIT
ROLLBACK
~~~
> juste pour INSERT/DELETE/UPDATE 
