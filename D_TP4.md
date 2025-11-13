# TP 4 
## VOL 
### 1 
#### SQL 2 
~~~SQL
select iin_vols.depart,iin_vols.arrivee,iin_vols.nvol,iin_avions.capacite from iin_vols join iin_avions on iin_vols.navion = iin_avions.navion;
~~~
#### SQL 1 
~~~SQL
select iin_vols.depart,iin_vols.arrivee,iin_vols.nvol,iin_avions.capacite from iin_vols , iin_avions where iin_vols.navion = iin_avions.navion;
~~~
#### AR 
* r1 = proj(iin_avions, {navion, capacite})
* r2 = proj(iin_vols, {navion, depart, arrivee})
* r3 = join(r1, r2, r1.navion = r2.navion)
### 2 
#### SQL 1 
~~~SQL
select distinct p.nom from iin_pilotes p join iin_vols v on p.npilote = v.pilote where v.navion = 8;
~~~
#### SQL 1 
~~~SQL
select distinct p.nom from iin_pilotes p,iin_vols v  where v.pilote = p.npilote and v.navion = 8;
~~~
#### R imbrique 
~~~SQL
select distinct nom from iin_pilotes where npilote in(select pilote from iin_vols where navion = 8);
~~~
#### AR 
* r1 = rest(iin_vols,navion = 8)
* r2 = proj(r1,{})
* r3 = proj(iin_pilotes,{npilote,nom})
* r4 = join(r2,r3,r2.pilote=r3.pilote)
* res = proj(r4,{nom})

### 3
#### SQL 2 
~~~sql
select distinct p.nom, v.depart,v.arrivee from iin_pilotes p left join iin_vols v on p.npilote = v.pilote order by p.nom,v.depart,v.arrivee;
~~~
#### SQL 1 
~~~sql
select distinct p.nom, v.depart,v.arrivee from iin_pilotes p, iin_vols v where p.npilote = v.pilote(+) order by p.nom,v.depart,v.arrivee;
~~~
#### AR 
* r1 =proj(iin_vols{pilote,depart,arrivee})
* r2 = proj(iin_pilotes,{nom,npilote})
* r3 = left-join(r2,r1,r2.npilote=r1.pilote)
* r4 = proj(r3,{nom,depart,arrivee})
### 4 
#### SQL 2 
~~~sql
select distinct p1.nom,p2.nom from iin_pilotes p1 join iin_vols on p1.npilote = iin_vols.pilote join iin_pilotes p2 on p2.npilote = iin_vols.copilote where upper(iin_vols.depart)='PARIS' and upper(iin_vols.arrivee)='NICE';
~~~
#### sql 1 
~~~sql
select distinct p1.nom,p2.nom from iin_pilotes p1 ,iin_pilotes p2,iin_vols v where p1.npilote = v.pilote and p2.npilote = v.copilote and upper(v.depart)='PARIS' and upper(v.arrivee)='NICE';
~~~
#### AR 
* r1 = proj(iin_pilotes{nom,npilote})
* r2 = proj(iin_pilotes{nom,npilote})
* r3_res = rest(iin_vols,depart = Paris and arrivee = Nice)
* r3 = proj(r3_res,{pilote,copilot})
* r4 = join(r1,r3,r1.npilote = r3.pilote)
* r5 = join(r4,r2,r4.copilot = r2.npilot)
* res = proj(r5,{nom})
