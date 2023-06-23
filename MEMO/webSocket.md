### The WebSocket API (WebSockets)

The WebSocket API is an advanced technology that makes it possible to open a two-way interactive communication session between the user's browser and a server.
With this API, you can send messages to a server and receive event-driven responses without having to poll the server for a reply.

서버 폴링없이 서버와 양방향 통신 가능 

### Interfaces
WebSocket
The primary interface for connecting to a WebSocket server and then sending and receiving data on the connection.

CloseEvent
The event sent by the WebSocket object when the connection closes.

MessageEvent
The event sent by the WebSocket object when a message is received from the server.


### Creating a WebSocket object
``` webSocket = new WebSocket(url, protocols);```

### protocols ?

 웹 소켓 연결을 설정할 때 사용되는 서브프로토콜(subprotocol) 

 클라이언트와 서버 간의 통신 규약을 정의 

선택적으로 사용 (optional)

예시 - 
웹 소켓을 사용하여 실시간으로 주식 시세 정보를 받는 애플리케이션

```js
// 서버에서 클라이언트의 요청을 처리하는 예시 코드
const server = new WebSocket.Server({ port: 8080 });

server.on("connection", (socket, request) => {
  const protocols = request.headers["sec-websocket-protocol"];
  const supportedProtocols = ["stock-quotes", "stock-updates"];
  
  const selectedProtocol = protocols.find(protocol => supportedProtocols.includes(protocol));
  
  if (selectedProtocol) {
    // 선택된 프로토콜에 따라 처리
    if (selectedProtocol === "stock-quotes") {
      // 주식 시세 정보 전송 로직
    } else if (selectedProtocol === "stock-updates") {
      // 주식 업데이트 정보 전송 로직
    }
  } else {
    socket.close(1002, "Unsupported protocol");
  }
});
```
client - new WebSocket을 호출할 때, protocols 매개변수에 ["stock-quotes", "stock-updates"]를 전달

server - 서버 측에서는 클라이언트가 전달한 서브프로토콜 목록을 확인

