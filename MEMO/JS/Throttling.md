### Throttling

많은 이벤트 발생 시 이벤트를 한 번에 처리

```js 
let timer;

if (!timer) {
		timer = setTimeout(function() {
		console.log("타이머 설정", "timer:", timer)
		console.log("이벤트 처리", "timer:", timer)
		timer = null;
		console.log("타이머 해제", "timer:", timer)            
}, 3000);
```


![Untitled (27)](https://github.com/HYO00/TIL/assets/79884004/219661dc-9d0a-47c5-ad7f-ac5dee3fd2a8)
