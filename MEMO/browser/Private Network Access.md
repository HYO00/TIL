## Private Network Access

사설 네트워크 접근 
chrome은  W3C 사양인 ‘사설망 접근(Private Network Access, PNA)’을 통해 **비 인증된** 웹사이트에서 비공개 네트워크 엔드포인트에 직접 액세스하는 것을 더 이상 사용하지 않는다고한다. 

why?
브라우저를 통해 침투하는 방식의 해킹 공격 보호 
cross-site request forgery (CSRF) attacks 으로부터 보호


### PNA CORS 발생 상황
- public 네트워크 사이트 → private 네트워크 사이트
  
- public 네트워크 사이트 → 로컬 호스트
  
- private 네트워크 사이트 → 로컬 호스트

- 도메인이 씌워져 있을 경우에만 발생


### PNA CORS 헤더 설정 

`Access-Control-Allow-Private-Network` 헤더 설정

1. 클라이언트 요청 헤더에 `ccess-Control-Request-Private-Network: true` 를 실어 서버에 예비 요청(Preflight) 보내기
2. 서버도 헤더에 Access-Control-Allow-Private-Network: true 를 통해 허락이나 불허를 응답
3. 엑세스 허락이 되면 본요청 통신

### PNA CORS 헤더 설정  이외 해결 방법

1. 요청 주체 변경

  호출하는 주체를 HTTPS로 설정 -> 가져오는 리소스 HTTP 여도 ok

  요청 리소스를 공인 네트워크로 변경 
  
2. 브라우저 옵션 변경 

chrome://flags

edge://flags

Block insecure private network requests 항목, Send Private Network Access preflights 항목의 설정값을 Disabled로 설정

가장 이상적인 방법은 `Access-Control-Allow-Private-Network` 헤더 설정을 하는것이다. 

