# mysql

### 명령어

`CREATE DATABASE`: 새 데이터베이스를 생성

예시: `CREATE DATABASE mydatabase;`

<br/>

`DROP DATABASE`: 데이터베이스를 삭제

예시: `DROP DATABASE mydatabase;`

<br/>

`USE`: 특정 데이터베이스를 사용

예시: `USE mydatabase;`

<br/>

`CREATE TABLE`: 새 테이블을 생성

예시:`CREATE TABLE mytable (
id INT PRIMARY KEY,
name VARCHAR(50),
age INT
);`

<br/>

`DROP TABLE`: 테이블을 삭제

예시: DROP TABLE mytable;

<br/>

`SELECT`: 데이터를 조회

예시: `SELECT * FROM mytable;`

<br/>

`INSERT INTO`: 테이블에 데이터를 삽입

예시: `INSERT INTO mytable (id, name, age) VALUES (1, 'John', 25);`

<br/>

`UPDATE`: 테이블의 데이터를 업데이트

예시: `UPDATE mytable SET age = 30 WHERE id = 1;`

<br/>

`DELETE FROM`: 테이블에서 데이터를 삭제

예시: `DELETE FROM mytable WHERE id = 1;`

<br/>

---

### SELECT

SELECT COUNT AS ContentCount

AS 별칭 

MySQL에서 유형별로 갯수를 가져오고 싶은데 COUNT 함수로 데이터 조회시 전체 갯수만 조회 

유형별로 갯수 조회하고 싶을 땐? 

컬럼에 데이터를 그룹화 할 수 있는 GROUP BY

특정 컬럼을 그룹화 하는 **GROUP BY**

특정 컬럼을 그룹화한 결과에 조건을 거는 **HAVING**

WHERE는 그룹화 하기 전이고, HAVING은 그룹화 후에 조건

GROUP BY 

- 테이블(데이터 행으로 축척)의 레코드(table 한행에 저장)를 grouping
- 각각의 그룹에 대해 하나의 행
- 1개 이상의 column에 대해 grouping
- SELECT 절에는 GROUP BY에 쓰인 column만 사용가능

**그룹 함수**

[제목 없는 데이터베이스](https://www.notion.so/3a9ca7b2ce80412f96fef3bfeba99567?pvs=21)

- 반드시 하나의 값만을 반환한다.
- NULL 값은 무시된다.
- NULL 값이 무시되지 않으려면 NVL, NVL2와 같은 함수를 이용한다.
- GROUP BY 설정 없이 일반 컬럼과 기술될 수 없다.

### DELETE, TRUNCATE, DROP 명령어의 차이점

DELETE - 데이터는 지워지지만 테이블 용량은 줄어 들지 않는다. 원하는 데이터만 지울 수 있다. 삭제 후 잘못 삭제한것을 되돌릴 수 있다.

TRUNCATE - 명령어는 용량이 줄어 들고, 인덱스 등도 모두 삭제 된다. 테이블은 삭제하지는 않고, 데이터만 삭제한다. 한꺼번에 다 지워야 한다. 삭제 후 절대 되돌릴 수 없다.

DROP - 데이블 전체를 삭제, 공간, 객체를 삭제한다. 삭제 후 절대 되돌릴 수 없다.

reference

https://wikidocs.net/4021

`ALTER TABLE`: 테이블의 구조를 변경

예시: `ALTER TABLE mytable ADD COLUMN email VARCHAR(100);`
