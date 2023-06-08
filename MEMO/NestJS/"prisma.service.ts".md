### prisma.service.ts ?

NestJS 프레임워크에서 Prisma ORM을 사용하는 서비스를 정의하는 파일
Prisma 클라이언트를 만들고 애플리케이션에서 사용할 수 있도록 프레임워크에 연결하는 역할

사용 방법 
1. 패키지 설치

```npm install @nestjs/prisma```

2. prisma.service.ts 파일을 생성하고, Prisma 클라이언트를 초기화

```
import { PrismaClient } from '@prisma/client';

export const prisma = new PrismaClient();
```

3. 해당 파일을 'app.module.ts'에 등록하여 사용

```
import { Module } from '@nestjs/common';
import { prisma } from './prisma.service';

@Module({
  providers: [
    {
      provide: 'PrismaService',
      useValue: prisma,
    },
  ],
  exports: ['PrismaService'],
})
export class AppModule {}
```

정리
- 복잡한 SQL 쿼리를 직접 작성하지 않고도 데이터베이스에 접근
- Prisma의 간편한 API를 사용하여 데이터를 검색, 생성, 수정, 삭제
- Prisma는 자동으로 TypeScript 코드를 업데이트
- Prisma를 사용하면 데이터베이스 스키마를 정의하고 데이터 모델을 작성
- Prisma는 데이터베이스 쿼리를 자동으로 최적화
