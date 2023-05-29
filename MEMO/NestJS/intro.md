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
