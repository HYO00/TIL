### Array.prototype.entries()

`entries()` 메서드는 배열의 각 인덱스에 대한 키/값 쌍을 가지는 새로운 Array Iterator 객체를 반환한다. 

```js 
const array1 = ['a', 'b', 'c'];

const iterator1 = array1.entries();

console.log(iterator1)
//Array Iterator {}

console.log(iterator1.next())
// { value: (2) [0, 'a'] , done: false }

console.log(iterator1.next().value);
// Expected output: Array [0, "a"]

console.log(iterator1.next().value);
// Expected output: Array [1, "b"]
```

배열에 `entries()` 메서드를 통해 Iterator 객체룰 만들고  Iterator 객체는 next 메소드를 가진다. 

iterator protocol 은 데이터 컬렉션을 순회하기 위한 프로토콜(미리 약속된 규칙)이다. 
