# TP 3
## exo 1
1) select depart,substr(depart,1,3) from iin_vols;
2) select depart,upper(substr(depart,1,3)) from iin_vols;
3) SELECT upper(substr(depart, 1, 3)) || nvol "Code des Vols" FROM iin_vols where lower(depart) LIKE 'l%' ORDER BY lower(depart), nvol DESC;
4) select distinct 'Vols de '|| depart || ' a ' || arrivee "Trajet" from iin_vols;  
5) select nvol, depart from iin_vols where navion in (select navion from iin_avions where upper(type)='AIRBUS') order by depart, nvol;
6) select nvol from iin_vols where depart in (select depart from iin_vols where nvol = 108);
7) select ename,round(sal* 0.853479),round(comm* 0.853479),trunc((sal+nvl(comm,0))* 0.853479,2) "revenu",ceil(((sal+nvl(comm,0))* 0.853479)*12) "revenu annuelle" from emp;
8) select nom,metier, substr(nom,1,5)||metier"abv" from iin_gaulois order by sexe,"abv";

## exo 2



