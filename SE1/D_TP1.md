---
tags: [D1]
title: D TP1
created: '2025-09-10T13:58:11.413Z'
modified: '2025-09-10T15:16:23.257Z'
---

# D TP1
## exo 2
1) SELECT * FROM dept; / r = proj(dept,{*})
2) SELECT * FROM dept WHERE deptno > 10; / r = restric(dept, deptno >10) res = proj(r,{*})
3) select * from dept order by loc;
4) select ename,mgr from emp;/ r = proj(emp,{ename,mgr})
5) select * from emp where job ='SALESMAN';
6) select ename,job,sal from emp where job ='ANALYST' or job = 'MANAGER'; 
7) select empno,ename from emp where mgr is null;
8) select empno,ename from emp where empno between 7800 and 7899;
9) select empno,ename from emp where ename like 'A%';
10) select ename,job,round((sal*0.82),2) from emp; 
11) select distinct job from emp;
12) select distinct job from emp;
13) select * from dept where deptno > 20;
14) select * from emp where job ='ANALYST' or job='CLERK';
15) select * from emp where ename like '_L%';
16) select * from emp where comm is null;
17) select * from emp order by job,sal desc;
18) select * from emp where job in('CLERK','MANAGER') and deptno =10;
19) select ename,sal from emp where sal >3000;
20) select ename"Nom",sal"Salaire" from emp;
21) select ename,greatest(sal,comm) from emp where job='SALESMAN';
22) select * from emp order by deptno desc, sal;
23) select ename,sal*1.32 from emp where deptno = 20;
24) select empno from emp where deptno in(20,10) and mgr is null;
25) select * from emp where (ename like '%J%' or ename like '%K%') and job != 'MANAGER' order by ename,deptno;
26) select * from dept where dname like '%L%L%';
27) select sal,job from emp order by job,sal desc;
28)  select empno,ename,job from emp where deptno not in (10,20,30);
29) select distinct deptno from emp;
30) select ename, sal, job from emp where sal > 12000 and job not in ('ANALYST','CLERK','MANAGER');



