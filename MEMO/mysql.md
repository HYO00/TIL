# mysql

명령어

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

`ALTER TABLE`: 테이블의 구조를 변경

예시: `ALTER TABLE mytable ADD COLUMN email VARCHAR(100);`
