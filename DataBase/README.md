
# **Database** 

`DataBase Mangement System ( DBMS )` : 서로 관계있는 Data들의 모임과 그 Data를 관리하기 위한 프로그램의 집합

`Database :` Data들의 집합

### Data의 추상화

`physical level` : 추상화의 최하위 단계, Data가 실제로 어떻게 되는지 파악

`logical level` : 어떤 ( what ) Data 가 있는 지 기술, 물리적 Data 독립성

`view level` : 추상화의 최상위 단계, 전체 Data의 일부분만 보여줌

#### Instance와 Schema

`Instance` : 어느 특정한 순간에 저장된 Data의 모임

`Schema` : DataBase의 전체적인 설계

`physical Schema` : 물리적 단계에서 DataBase 설계 기술

`Logical Schema` : 논리적 단계에서 DataBase 설계 기술

`Sub Schema` :  View 단계에서 DataBase 스키마 

#### DataBase Model 

`DataBase Model`이란, Data , Data 사이의 관계, Data의 의미 , 일관성 제약조건 등을 기술한 개념적 표현들의 집합 ex) 관계형 모델, 개체 - 관계 모델, 객체-기반 데이터 모델, 반구조형 데이터 모델



`DDL`  : DataBase 스키마를 기술합니다 ( ex) drop, alter, create ) 

`DML` : DataBase의 질의 및 갱신 (ex) select, insert, delete, update )

`DCL` : DataBase의 객체 권한 등의 부여 ( ex) commit, rollback, grant, revoke )



#### DataBase의 무결성 조건

* 개체 무결성 제약조건 : 존재하고 있는 사실은 반드시 유일하게 식별되어야 한다.
* 참조 무결성 제약조건 : 참조하는 사실은 반드시 존재하여야 한다.



#### Entity - Relationship

개체 ( Entity ) : 기본적인 객체를 나타내는 것

관계 ( Relationship ) : 여러 개체들관의 연관성 



#### 정규화 

`정규화`란, 관계형 데이터베이스의 설계에서 중복을 최소화하게 데이터를 구조화하는 프로세스이다.

- 하나의 테이블에는 하나의 주제만 있어야 한다.



#### Transaction ( 트랜잭션 )

데이터베이스의 응용 프로그램에서 하나의 논리적 기능을 수행하는 연산들의 모임을 `트랜잭션`이라고 합니다.

트랜잭션의 ACID

* `A(Atomicity)` : all or none
* `C(consistency)` : 정확성에 관한 요구 조건
* `I(isolation)` : 다른 트랜잭션에게 영향을 받지 않음
* `D(Durability)` : 영속성의 요구 조건 ( 작업 후 Database의 변화는 같아야 합니다. )



#### Client와 Server

`Client` : Database에 접속하여 작업

`Server` : DataBase System이 실제로 설치되어 있는 것 



#### Data Mining

`Data Mining`이란 , 유용한 패턴을 찾기 위해 대규모 데이터베이스를 반자동적으로 분석하는 작업



#### DBA(Database administrator)

Data와 Data Access Program 모두를 관리하는 사람 



#### DataBase 용어

* table = relation
* tuple = row
* attribute = column 
* domain = 한 column의 모든 값

relation instance, relation schema

#### DataBase key

* super key : 한 relation에서 유일하게 식별 가능한 속성
* candidate key : primary 키가 될 수 있는 key들 ( 최소성, 유일성 )
* primary key
* alternate key :  primary key를 제외한 나머지 super key
* foreign key : 다른 table을 참조하는 key



#### Schema Diagram

Schema Diagram은 시각적으로 table사이의 연관성을 표현한다.



#### query language

질의어란, 사용자가 database로부터 정보를 요청할 때 사용하는 언어입니다.

join 연산 : 두개의 연산을 합치는 연산

카티션 곱 :  두개의 연산을 (A*B) 곱하는 연산



## 기본적인 query 연산

Table 생성

```
create table setter(
set_into varchar(20) not null,
set_number numeric(7,2),
set_Test varchar(50),
primary key set_into,
foreign key (testtable) references set test
on delete cascade
on update cascade

                    );
```



## Clustered Index & Non - Clustered Index

`Clustered Index` : 물리적으로 행을 재배열하며, 테이블당 1개 생성 가능합니다.

즉 물리적으로 행을 재배치 한다는 것입니다.

`Non - Clustered Index` : 별도의 인덱스 Table을 만들어 Data를 검색하며, 공간을 많이 차지합니다.



### SubQuery

`SubQuery`는 완전한 Select 문을 ( ) -> 괄호를 이용하여 `AS Name` 으로 별칭을 주는 것입니다.
즉, 완벽한 Select Sql문을 이용하여, `Database`의 `CRUD`를 하는데 이용하는 `Query`문입니다.

```sql
Select B.A, B.B , (
Select C.A
From C 
    inner join D
    ON C.A = ON D.A
    Where C.A = B.A
) as Example
From B
```

이를 통해 단일 `Row`에 있는 한 `Column`의 값을 0~1개 반환할 수 있습니다.

또한 `Select` , `Set`, `From` , `Insert`문 모두 `SubQuery`를 사용할 수 있습니다.


```sql

Update Test Set TestRow = ( Select * From TestBTable ); 
// Update문에서도 Select SubQuery를 이용해 Set 할 수 있습니다.

```

```sql

Select * 
From 
(Select Test.A,
Test.B, 
Test.C
From Test
Where Test.C = 'value' ) as SubQuery 
// From절에서도 이러한 중첩을 통해 Table 중첩이 가능합니다. 
```

```sql
Insert Into Test Values(
(Select * From A),
(Select * From B)

); 
// Insert문에서도 조건을 사용하여 중첩이 가능합니다.
```
