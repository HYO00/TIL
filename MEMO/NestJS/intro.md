# NestJS

### NestJS?

Node.js 기반의 서버 사이드 애플리케이션 개발을 위한 프레임워크

- controller.ts
    - 라우팅
    - **`@Controller`** API 엔드포인트를 정의하는 데 사용되는 데코레이터
    - 클래스를 컨트롤러로 선언
        
        ```jsx
        //데코레이터 가져오기
        import { Controller, Get, Post } from '@nestjs/common';
        //비즈니스 로직 가져오기
        import { AppService } from './app.service';
        
        @Controller('monday')
        export class AppController {
          constructor(private readonly appService: AppService) {}
        
          @Get()
          getHello(): string {
            return this.appService.getHello();
          }
        
          @Post()
          postHello(): string {
            return this.appService.postHello();
          }
        }
        ```
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8e05bcab-4915-4df5-97de-a43b34e3f644/Untitled.png)
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fd43dbdb-c2b2-45ee-b0d9-4825457685f2/Untitled.png)
        
- module.ts
    
    의존성 주입 
    
    ```jsx
    import { Module } from '@nestjs/common';
    import { AppController } from './app.controller';
    import { AppService } from './app.service';
    
    @Module({
      imports: [],
      controllers: [AppController],
      providers: [AppService], 
    })
    export class AppModule {}
    ```
    
- service.ts
    
    비즈니스 로직 처리
    ```js
    import { Injectable } from '@nestjs/common';
    //주입 
    @Injectable()
    export class AppService {
      getHello(): string {
        return 'today is monday';
      }

      postHello(): string {
        return 'monday is over';
      }
    }
    ``` 


- DTO(Data Transfer Object)
 데이터 전송 객체 
컨트롤러에서 DTO를 사용해 클라이언트로부터 전달된 데이터를 검증, 서비스에서 유효성 검사를 통과한 DTO를 기반으로 사용자를 생성하거나 데이터베이스에 저장 
→ 데이터의 일관성과 유효성을 보장, 코드 가독성 재사용성 향상
