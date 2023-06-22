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
