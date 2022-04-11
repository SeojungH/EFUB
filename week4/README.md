# EFUB 4주차 세미나 과제

###### {백인턴} {황서정}



### 01. 학사 정보 관리 ERD

https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1&title=Untitled%20Diagram.drawio#R7VtZc6M4EP41eowLHVyPxibZ2koqU0lqd%2FaRNRqbLQwujGM7v34FCHPJBnu4vDsvKdSALH19fN0tAvBsfXgKrM3qxbepC5BkHwCeA4RUDbG%2FkeCYCAhWEsEycOxEBDPBu%2FNFuVDi0p1j023hwdD33dDZFIUL3%2FPoIizIrCDw98XHfvhu8Vc31pJWBO8Ly61K%2F3TscJVINaRm8t%2Bos1ylvwwVPbmzttKH%2BU62K8v29zkRNgGeBb4fJlfrw4y6EXYpLsl7j2funhYWUC9s8sKTe%2Fjd%2Bef5D%2Ffjebd9dx5e94bzgJNZPi13xzcMzCkwZKBLwJwBTQO6xpcfHlNM9isnpO8baxGN90ztABurcO2yEWSXlussPXa9YAujARNUV8oX%2F0mDkB5yIr7yJ%2BqvaRgc2SPp3RRWbkZQ5qjuM6VAictWOYUQLrO4HSxPU2dQsQuO1hXIQVKFrgwUtZkt8SHbuxMe36hrhY7vmdkd44fvhdzwISpCST17GhkxG5pvvkc%2F%2FBfLYxAY29AKwvSWx%2B4wWeDvPJtGa5biV9kuv%2BcHf0WDiZwO54f8zfmRj84qa%2BvvggXf2OPzl6qYsv7y%2BmxoGKPZ3MQPfP9sZUsaXkJOTh6M0Lmo%2BzrdnoRBjOpn0WVFGue%2F8c132OZOxoVUUjQutWQ0ydb5W3kXK02ESc1ECTaViWIDPG38J2xSFrszBsYMmAaYTsFUH4M7y%2FLY3BkJ3JkFQH0ODBJDpwOdpJJZ1dNdlzFS5IUDoJmCwsE8cedwYIrsMA%2BmAjQyagyhMjiGSgN%2ByeiBc0AOpSIdNArrl1KE2rCOmob1n4zWGBVVhfUbozXRaibqOFqnOWRLGqYHJ4z5fgJlPowYH04kqPJxRvnR4JgbfKOBw%2FYTeVNf5kL%2BJ%2BbC9Gcdc49toge2nRiULgi7c6CzbF6Ps3kcheAR0D%2FGRfrH2tDRFkMBdHdC%2F5igAppEl4dGE90f%2F5cyUiIPDmKTAvMKehDXg21UgxeDUS0RpMbSNREgTS5oGN5MBKRmoo7zBizIrlvJGwppw8WUoQ%2BzgL%2FM4jqzGEvBIFKxsGHUuBE0FhUjWZsohCiKpBNJUZGsFuaVIZlAgiCWFYRVDGFX%2Br%2FUfiv3fqQo%2F0vIV9DK3a6sTXQZrPz13zu2UGOTqwS4NFccDJPf4KL6iCBbRAJqVlqgZiHUgq55xdNabP1yVy30fM23teXZr303fpuWfJcsdDx93%2FKhwq1930o7s7u%2BrxBYUbstX%2FfFpzgs7zZQdG3GkcCoBoPbE%2FDYjvlEpB2vV0rl9knpfSTkQpTHwq8pbdb6W0%2F0KqslTeEb3UjFNRN17EaCflz19CS5SDOKsZSvil6Crs%2BOihBM7d68Re3HWxR0RlNXe0s5QJYn6thbRM3GyqcDd0Y65VOgwTknPcrrtgk0Qd19FdC43u%2FH%2FXD5sPTmnE%2Bqmahj90ury1KPdaoCFgeY22mPoh7rPdR7CJ9BdrB6DzYp%2BG7xwgnEuOiJOBOcccV4VD6vO1sbxjcenWi%2FPVV5sKfG3X%2FHk69r9JtvXzTwP%2FzXOiOzr1X7RXXWH%2Bjqv%2FR%2Bnd4vlu1p4jTqfAnBAU%2FNxKAKqvQsG037ofdIizIsmas%2BOC22%2FAFLIWKVGK3y8WsrnNb8qEIZJrgR1FJwq0zUdXC7rv4vKvisiYg%2Bey5bQ2vEpzQkvr6OsSrEd2vnoEJ8rXUO2DD7h4bk8ey%2FQrD5Lw%3D%3D


![Untitled Diagram drawio](https://user-images.githubusercontent.com/86144019/162711174-58b629a7-612f-4333-a964-749a25312ad0.png)



### 02. MySQL 실습 코드

##### SWS 테이블 생성 코드

```
create database efub;
use efub;

create table SWS (
sws_id BIGINT NOT NULL auto_increment,
teamname varchar(45) NOT NULL,
PRIMARY KEY(sws_id)
);

insert into SWS(teamname) values
("베이커리"),
("라꾸라꾸"),
("STEADY"),
("梨상청");
```

##### member 테이블 생성 코드

```
create table member(
member_id BIGINT NOT NULL auto_increment,
name varchar(45) NOT NULL,
position varchar(45) NOT NULL,
email varchar(200) NULL,
birth_date DATE NULL,
sws_id BIGINT NOT NULL ,
PRIMARY KEY(member_id),
FOREIGN KEY(sws_id) REFERENCES SWS(sws_id)
);

insert into member(name, position, email, birth_date, sws_id) values
("윤효정", "back", "efub@gmail.com", "1998-03-23", 3),
("김시연", "back", "siyeon@gmail.com", "1999-07-26", 1),
("이해린", "front", "ocean@naver.com", "2000-04-22", 4),
("황서정", "back", "hseojung@gmail.com", "2001-04-27", 4);

```

##### JOIN 코드

```
select name, position, email, birth_date from member LEFT JOIN SWS ON SWS.sws_id  = member.sws_id
union
select name, position, email, birth_date from member RIGHT JOIN SWS ON SWS.sws_id  = member.sws_id;
```



##### JOIN 출력 결과

![image](https://user-images.githubusercontent.com/86144019/162731872-1203d02c-6946-42e8-abaf-7814ec5e19f1.png)
