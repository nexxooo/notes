# TP D 5
## Base Vols
### 1 
~~~sql
select count(*),max(capacite) from iin_avions where upper(type) ='AIRBUS';
~~~
### 2 
~~~sql
select sum(capacite) from iin_avions;
~~~ 
### 3 
~~~sql 
select navion from iin_avions where capacite in (select max(capacite) from iin_avions where upper(type)='AIRBUS') and upper(type)='AIRBUS' ;
~~~
### 4 
~~~sql
select count(*) from iin_vols where (lower(depart) = 'strasbourg' or lower(depart)='lyon') and (lower(arrivee)= 'strasbourg' or lower(arrivee)= 'lyon');
~~~
### 5 
~~~sql 
select trunc(avg(capacite),2) from iin_avions where lower(type) ='airbus' and navion in (select navion from iin_vols where lower(depart)='paris' and lower(arrivee)='nice');
~~~ 
### 6 
~~~sql 
select count(*) from iin_vols v join iin_pilotes p on v.pilote = p.npilote where lower(p.nom) = 'dupont';
~~~


