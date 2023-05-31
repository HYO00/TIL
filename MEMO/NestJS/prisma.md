# prisma

Node.js와 TypeScript ORM

### prisma folder

```jsx
//데이터 베이스 연동
schema.prisma 
 

//model 만들기
model User {
  id    Int     @default(autoincrement()) @id
  email String  @unique
  name  String?
  password String
  role String
}

//migration 
// schema.prisma file을 읽어 현재 데이터베이스 상태와 비교해 차이가 있는 경우 마이그레이션 파일을 생성 
//마이그레이션을 적용해 데이터베이스 스키마를 최산 상태로 업데이트
npx prisma migrate dev

create user_table
```

*npx - node.js와 함께 제공되는 패키지 실행 도구로, 로컬에 설치된 패키지를 실행하는데 사용

<img width="628" alt="스크린샷 2023-05-31 오후 11 33 45" src="https://github.com/HYO00/TIL/assets/79884004/3ea53f90-fb5d-4927-9d92-a835554406be">

prisma Client

데이터베이스에 대한 쿼리 및 데이터 조작 기능을 제공하는 prisma ORM의 핵심 패키지

데이터베이스와 상호작용 

```jsx
npm install @prisma/client

//모듈 만들기
nest generate module user

//컨트롤러 만들기
nest g controller user/controller/user --flat

//서비스 만들기 
nest g service user/service/user --flat
```
test

<img width="500" alt="image" src="https://github.com/HYO00/TIL/assets/79884004/58b750af-0d20-4583-9685-9101e5620e6e">
