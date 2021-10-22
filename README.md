# student-info
Student Information in the form of code.

create table sreekar.student(
		id serial primary key,
		firstname varchar(50),
		lastname varchar(50),
		age integer,
		gender character(7),
		mobile_number character(10),
		parent_id character(25) references sreekar.parent(parent_code),
		marks_id character(20) references sreekar.marks (marks_code),
		address_id integer references sreekar.address(address_code),
		classteacher character(20) references sreekar.teacher(teacher_code),
		classroom_id character(20) references sreekar.classroom(classroom_code),
		std_dateofjoining timestamp(6) with time zone default now()
                                );
								
select * from sreekar.student

insert into sreekar.student values('100','Dhamani','Sharma','14','Female','7896320001','P100','MK100','100','TC100','Civ100');
insert into sreekar.student values('101','Kiran','Kumar','15','Male','8519643366','P101','MK101','101','TC101','Cv100');
insert into sreekar.student values('102','Hema','Sree','14','Female','7896321101','P102','MK102','102','TC102','Cvi100');
insert into sreekar.student values('103','Gayathri','Sharma','13','Female','7996320001','P103','MK103','103','TC103','Cvii100');
insert into sreekar.student values('104','Harsha','Vardhan','13','Male','7796320001','P104','MK104','104','TC104','Cviii100');
insert into sreekar.student values('105','Surya','Narayana','14','Male','7893320001','P105','MK105','105','TC105','Cix100');
insert into sreekar.student values('107','Shiva Narayana','Murthy','16','Male','9638521147','P107','MK107','107','TC106','Cix100');
insert into sreekar.student values('108','Narayana','Murthy','14','Male','6699220001','P108','MK108','108','TC108','Cxii100');
insert into sreekar.student values('109','Subrahmanya','VVV','14','Male','7755883301','P109','MK109','109','TC109','Cxiii100');

create table sreekar.parent(
		parent_code character(25) primary key,
		p_firstname varchar(50),
		p_lastname varchar(50),
		spousename varchar(50),
		p_age integer,
		email_id text,
		p_mobilenumber character(10),
    	parent_occupation character(50)
                            );
							
select * from sreekar.parent	

insert into sreekar.parent values('P100','Ravi','Kumar','Lalitha Chandra Hasa','38','ravi@gmail.com','7892520012','Doctor');
insert into sreekar.parent values('P101','RamBabu','---','Renuka','36','rambabu@gmail.com','9638541025','BSNL Officer');
insert into sreekar.parent values('P102','Hemanth','Kumar','Jahanavi','35','hemanth@gmail.com','7892520112','Software Engineer');
insert into sreekar.parent values('P103','Sri','Chaitayna','Mounika Choudari','30','chaitayna@gmail.com','7995520012','Business');
insert into sreekar.parent values('P104','Bala','Chandra','Swathi Kumari','30','bala@gmail.com','8892520012','Software');
insert into sreekar.parent values('P105','Mani','Shankar','Priya Rani Reddy','29','shankar@gmail.com','7822521012','Govt. Teacher');
insert into sreekar.parent values('P107','Priya','Rani','Mani Shankar','30','rani@gmail.com','7778889992','Business Contractor');
insert into sreekar.parent values('P108','Venu','Thotampudi','Jayanthi','27','venu@gmail.com','9996662220','HR');
insert into sreekar.parent values('P109','Hema Sree','Reddy','Mani DeepKumar','24','hema@gmail.com','7775550001','Pharmastit');

create table sreekar.marks(
		marks_code character(20) primary key,
		telugu_marks integer,
		hindi_marks integer,
		english_marks integer,
		math_marks integer,
		science_marks integer,
		social_marks integer,
		total integer,
		percentage double precision,
		class_rank integer
                           );							
	
select * from sreekar.marks	

insert into sreekar.marks values('MK100','75','65','88','78','60','56','422','70.33','1');
insert into sreekar.marks values('MK101','65','65','68','68','60','60','386','64.33','11');
insert into sreekar.marks values('MK102','80','70','75','70','80','65','370','61.66','2');
insert into sreekar.marks values('MK103','75','65','88','78','60','56','422','70.33','6');
insert into sreekar.marks values('MK104','75','65','88','78','00','56','362','60.33','4');
insert into sreekar.marks values('MK105','85','85','88','88','80','86','512','85.33','1');
insert into sreekar.marks values('MK107','65','65','68','68','60','60','386','64.33','11');
insert into sreekar.marks values('MK108','55','55','58','65','50','50','333','55.5','21');
insert into sreekar.marks values('MK109','60','60','60','60','60','60','360','60','31');

create table sreekar.address(
		address_code integer primary key,
		lane1 varchar(50),
		street varchar(50),
		area varchar(50),	
		zipcode integer,
		city varchar(50),
		state character(25),
		country character(20)
                             );
							 
select * from sreekar.address

insert into sreekar.address values('100','H.No:5-3-449/1','Pakabanda Bazar','Khammam','507001','Khammam','TELANGANA','INDIA');
insert into sreekar.address values('101','H.No:6-3-549/1A','Srinagar Colony','Khammam','507003','Khammam','TELANGANA','INDIA');
insert into sreekar.address values('102','H.No:7-3-649/1F','Green Hills Colony','Kothapet','507011','Hyderabad','TELANGANA','INDIA');
insert into sreekar.address values('103','H.No:8-3-749/1D','Teachers Colony','Nagole','507021','Hyderabad','TELANGANA','INDIA');
insert into sreekar.address values('104','H.No:9-3-849/1E','Raghavendra Colony','Kondapur','500084','Secundrabad','TELANGANA','INDIA');
insert into sreekar.address values('105','H.No:4-3-949/1B','Vidhya Nagar','Khammam','507002','Khammam','TELANGANA','INDIA');
insert into sreekar.address values('106','H.No:3-3-249/1T','Doctors Colony','Tarnaka','507010','Hyderabad','TELANGANA','INDIA');
insert into sreekar.address values('107','H.No:2-3-149/2T','Sneha puri Colony','Nagole','507025','Hyderabad','TELANGANA','INDIA');
insert into sreekar.address values('108','H.No:1-1-159/1T','Neha puri Colony','Uppal','507022','Hyderabad','TELANGANA','INDIA');
insert into sreekar.address values('109','H.No:2-2-229/2T','Commerial Tax Colony','Nagole','507025','Hyderabad','TELANGANA','INDIA');

create table sreekar.teacher(
		teacher_code character(20) primary key,
		t_firstname varchar(50),
		t_lastname varchar(50),
		t_age integer,
		t_gender character(7),
		t_mobilenumber character(10),
		classteacher_for integer,
		teacher_expert_in varchar(25),
		year_of_experience_in character(25),
		teacher_emailid text
                              );
							  
select * from sreekar.teacher

insert into sreekar.teacher values('TC100','Zahkeer','Shaik','36','Male','8965204147','9','MATHEMATICS','16 Years','zahkeer@gmail.com');
insert into sreekar.teacher values('TC101','Mounika','Sree','32','Female','7896521001','4','ENGLISH','10 Years','sree@gmail.com');
insert into sreekar.teacher values('TC102','Manasa','Rao','30','Female','8965204177','5','TELUGU','14 Years','rao@gmail.com');
insert into sreekar.teacher values('TC103','Gopinath','Malhotra','26','Male','8960004147','7','PHYSICS','16 Years','gopinath@gmail.com');
insert into sreekar.teacher values('TC104','Harsha','Vardhan','33','Male','8742223336','6','SOCIAL','16 Years','harsha@gmail.com');
insert into sreekar.teacher values('TC105','Satish','Kumar','46','Male','9964412253','8','HINDI','17 Years','satish@gmail.com');
insert into sreekar.teacher values('TC107','Varsha','Kumari','39','Female','8889990002','11','Chemistry','18 Years','varsha@gmail.com');
insert into sreekar.teacher values('TC108','Deepthi','Pilli','28','Female','9996661110','12','Botany','03 Years','deepthi@gmail.com');
insert into sreekar.teacher values('TC109','Jayanthi','Kumari','27','Female','7775552220','13','Zoology','01 Years','jayanthi@gmail.com');

create table sreekar.classroom(
		classroom_code character(20) primary key,
		classroom_area character(225),
		classroom_seatting_area character(50),
		classroom_number_of_benches integer
                               );

select * from sreekar.classroom

insert into sreekar.classroom values('Civ100','550 SFT','60 Members','30');
insert into sreekar.classroom values('Cv100','450 SFT','60 Members','30');
insert into sreekar.classroom values('Cvi100','650 SFT','60 Members','30');
insert into sreekar.classroom values('Cvii100','550 SFT','60 Members','30');
insert into sreekar.classroom values('Cviii100','655 SFT','60 Members','30');
insert into sreekar.classroom values('Cix100','700 SFT','80 Members','40');
insert into sreekar.classroom values('Cxi100','700 SFT','80 Members','40');
insert into sreekar.classroom values('Cxii100','750 SFT','85 Members','42');
insert into sreekar.classroom values('Cxiii100','710 SFT','80 Members','40');


select A.id, A.firstname, A.lastname, A.age, A.gender, A.mobile_number,  A.std_dateofjoining, A.parent_id,
       B.p_firstname, B.p_lastname, B.spousename, B.p_age, B.email_id, B.p_mobilenumber, B.parent_occupation, 
	   A.marks_id, C.telugu_marks, C.hindi_marks, C.english_marks, C.math_marks, C.science_marks, C.social_marks, 
	   C.total, C.percentage, C.class_rank, A.address_id, D.lane1, D.street, D.area, D.zipcode, D.city, D.state, 
	   D.country, A.classteacher, E.t_firstname, E.t_lastname, E.t_age, E.t_gender, E.t_mobilenumber, 
	   E.teacher_expert_in, E.year_of_experience_in, E.teacher_emailid, A.classroom_id, F.classroom_area,
	   F.classroom_seatting_area, F.classroom_number_of_benches from sreekar.student A
	   inner join sreekar.parent B
	   on A.parent_id = parent_code
	   inner join sreekar.marks C
	   on A.marks_id = C.marks_code
	   inner join sreekar.address D
	   on A.address_id = D.address_code
	   inner join sreekar.teacher E
	   on A.classteacher = E.teacher_code
	   inner join sreekar.classroom F
	   on A.classroom_id = F.classroom_code

create or replace view VW_student
as(
	select A.id, A.firstname, A.lastname, A.age, A.gender, A.mobile_number,  A.std_dateofjoining, A.parent_id,
       B.p_firstname, B.p_lastname, B.spousename, B.p_age, B.email_id, B.p_mobilenumber, B.parent_occupation, 
	   A.marks_id, C.telugu_marks, C.hindi_marks, C.english_marks, C.math_marks, C.science_marks, C.social_marks, 
	   C.total, C.percentage, C.class_rank, A.address_id, D.lane1, D.street, D.area, D.zipcode, D.city, D.state, 
	   D.country, A.classteacher, E.t_firstname, E.t_lastname, E.t_age, E.t_gender, E.t_mobilenumber, 
	   E.teacher_expert_in, E.year_of_experience_in, E.teacher_emailid, A.classroom_id, F.classroom_area,
	   F.classroom_seatting_area, F.classroom_number_of_benches from sreekar.student A
	   inner join sreekar.parent B
	   on A.parent_id = parent_code
	   inner join sreekar.marks C
	   on A.marks_id = C.marks_code
	   inner join sreekar.address D
	   on A.address_id = D.address_code
	   inner join sreekar.teacher E
	   on A.classteacher = E.teacher_code
	   inner join sreekar.classroom F
	   on A.classroom_id = F.classroom_code
   )

select * from VW_student

drop view VW_student

create or replace function fun_cursor()
returns void as
$$
declare 
	cur cursor for select * from VW_student;
	rec record;
begin
	open cur; loop
	fetch cur into rec;
	exit when not found;
	raise notice '% % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % % %',rec.id, rec.firstname, 
	                rec.lastname, rec.age, rec.gender, rec.mobile_number, rec.std_dateofjoining, rec.parent_id, 
					rec.p_firstname, rec.p_lastname, rec.spousename, rec.p_age, rec.email_id, rec.p_mobilenumber,
					rec.parent_occupation, rec.marks_id, rec.telugu_marks, rec.hindi_marks, rec.english_marks, 
					rec.math_marks, rec.science_marks, rec.social_marks, rec.total, rec.percentage, rec.class_rank, 
					rec.address_id, rec.lane1, rec.street, rec.area, rec.zipcode, rec.city, rec.state, rec.country, 
					rec.classteacher, rec.t_firstname, rec.t_lastname, rec.t_age, rec.t_gender, rec.t_mobilenumber, 
					rec.teacher_expert_in, rec.year_of_experience_in, rec.teacher_emailid, rec.classroom_id, 
					rec.classroom_area, rec.classroom_seatting_area, rec.classroom_number_of_benches;
  	end loop;
  	close cur;
end;
$$ language 'plpgsql';

select fun_cursor()

select extract(minute from std_dateofjoining) as std_mins from VW_student

select extract(hour from std_dateofjoining -interval '3 hour' ) from VW_student

select extract(dow from std_dateofjoining) from VW_student

select extract (millisecond from std_dateofjoining) from VW_student

select extract(doy from std_dateofjoining) from VW_student

select date_part('year','2021-10-20 15:03:38.717059+05:30'::date) - date_part('year','2020-10-09 15:56:32.924214+05:30'::date)

select (date_part('year','2021-10-20 15:03:38.717059+05:30'::date) - date_part('year','2021-09-09 15:56:32.924214+05:30'::date)) * 12+
		(date_part('month','2021-10-20 15:03:38.717059+05:30'::date)- date_part('month','2021-09-09 15:56:32.924214+05:30'::date))
		
select date_part('day','2021-10-20 15:03:38.717059+05:30'::timestamp - '2021-10-10 15:56:32.924214+05:30'::timestamp)		

select trunc(date_part('day','2021-10-20 15:03:38.717059+05:30'::timestamp - '2021-09-29 15:56:32.924214+05:30'::timestamp)/7)

select date_part('day','2021-10-20 12:33:38.717059+05:30'::timestamp - '2021-10-19 11:33:51.030919+05:30'::timestamp) * 24 +
       date_part('hour','2021-10-20 12:33:38.717059+05:30'::timestamp - '2021-10-19 11:33:51.030919+05:30'::timestamp)

select date_part('hour','2021-10-20 12:33:38.717059+05:30'::timestamp - '2021-10-19 12:30:51.030919+05:30'::timestamp)*60+
       date_part('minute','2021-10-20 12:33:38.717059+05:30'::timestamp - '2021-10-19 12:30:51.030919+05:30'::timestamp)

select (date_part('day','2021-10-20 12:33:38.717059+05:30'::timestamp - '2021-10-19 12:30:51.030919+05:30'::timestamp)*24+
	    date_part('hour','2021-10-20 12:33:38.717059+05:30'::timestamp - '2021-10-19 12:30:51.030919+05:30'::timestamp))*60+
		(date_part('minute','2021-10-20 12:33:38.717059+05:30'::timestamp - '2021-10-19 12:30:51.030919+05:30'::timestamp))
		
select clock_timestamp()

