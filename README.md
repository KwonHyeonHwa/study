# study

select * from cslee.tab1;
select * from cslee.tb_accnt;
select * from cslee.tb_cust;
select * from cslee.tb_emp;
select * from cslee.tb_prod;
select * from cslee.tb_tran;
select * from cslee.tb_trcd;

select * from cust_name, reg_num, from cslee.tb_cust;



--1

select emp_name  사원이름, ORG_CD 소속, POSITION 직무, SALARY 연봉
from cslee.TB_EMP
where position = '대리';


--2

select count(*) from cslee.tb_emp;
select emp_name  사원이름, ORG_CD 소속, POSITION 직무, SALARY 연봉
from cslee.TB_EMP;

select emp_name  사원이름, ORG_CD 소속, POSITION 직무, SALARY 연봉
from cslee.TB_EMP
where salary >= 50000000; 


--3

select emp_name  사원이름, ORG_CD 소속, POSITION 직책, SALARY 연봉
from cslee.TB_EMP
where (org_cd = '08' or org_cd = '09' or org_cd = '10')
and position  = '사원'
and salary  >= 40000000
and salary  <= 50000000;



--4

select emp_name  사원이름, ORG_CD 소속, POSITION 직책, SALARY 연봉
from cslee.TB_EMP
where org_cd  in ('08', '09', '10')
and position = '사원'
and salary between  4000000 and 50000000;

select emp_name  사원이름,  SALARY 연봉
from cslee.TB_EMP
where salary  between 40000000 and 50000000;



--5

select emp_name, ORG_CD, POSITION, SALARY
from cslee.TB_EMP
where org_cd in ('06', '07')
and position in ('팀장', '과장');

select emp_name, ORG_CD, POSITION, SALARY
from cslee.TB_EMP
where (ORG_CD, POSITION) 
	in (('06', '팀장'), ('07', '과장'));



-- 6

select emp_name 사원이름, ORG_CD 팀코드, position 직책, ent_date 입사일자
from cslee.TB_EMP
where emp_name like '김%'; 

select emp_name 사원이름, ORG_CD 팀코드, position 직책, ent_date 입사일자
from cslee.TB_EMP
where emp_name like '_승%'; 



--7

select emp_name 사원이름, ORG_CD 팀코드, position 직책, gender 성별
from cslee.TB_EMP
where gender = null;

select emp_name 사원이름, ORG_CD 팀코드, position 직책, gender 성별
from cslee.TB_EMP
where gender is null;

--8

select emp_name 사원이름, ORG_CD 팀코드, position 직책
from cslee.TB_EMP
where org_cd ='10'
and not position = '팀장';

select emp_name 사원이름, ORG_CD 팀코드, position 직책
from cslee.TB_EMP
where org_cd  is not null;



--9

select  ORG_CD 팀부서, emp_name 사원이름, ent_date 입사일
from cslee.TB_EMP
order by org_cd, ent_date desc;

select  emp_name , emp_no, ORG_CD  
from cslee.TB_EMP
order by emp_name asc, emp_no asc, ent_date desc;

select  emp_name 사원이름, emp_no 사원번호, ORG_CD 부서코드  
from cslee.TB_EMP
order by 사원이름, 사원번호, 부서코드 desc;

select  emp_name , emp_no, ORG_CD  
from cslee.TB_EMP
order by 1 asc, 2 asc, 3 desc;

select  emp_name 사원이름, emp_no 사원번호, ORG_CD 부서코드  
from cslee.TB_EMP
order by emp_name, 2, 부서코드 desc;







