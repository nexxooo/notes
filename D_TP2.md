# TP2
## exo 1
1)  
~~~ 
r1 = restrict(iin-avions,type)
r2 = proj(r1,navion)
r3 = res(iin_vols,navion in r2)
res = proj(r3,{nvol})
~~~
2) select nvol from iin_vols where navion in (select navion from iin_avions where type = 'Airbus')
3) select * from iin_avions where capacite in (select capacite from iin_avions where navion = 4);
4) SELECT *
FROM iin_vols
WHERE navion IN (SELECT navion
FROM iin_vols
WHERE pilote IN (SELECT npilote
FROM iin_pilotes
WHERE nom='Dupont')
AND depart='Lyon')
5) le nom des pilotes qui ne sont pas arriver a nice
6) Destinations pour lesquelles les avions ont toujours au moins 300 places.
7) destination d'arrive et de depart ou il existe un chemin inverse 
8) select pilote from iin_vols where navion in (select navion from iin_avions where capacite < 200);
9) select distinct arrivee,depart from iin_vols where navion in (select navion from iin_avions where type ='Airbus' and capacite >= 300);
10) select nom from iin_pilotes where npilote not in (select copilote from 
11) select * from iin_vols where (pilote,depart) not in (select npilote,habite from iin_pilotes);




