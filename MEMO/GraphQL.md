# GraphQL

schema - 서버와 클라이언트가 주고 받을 데이터의 형식을 정의한 약속 

`schema`

```jsx

type Topic {
	id:Int!
  title:String!
  body:String
}

type Query {
	title:String!
	topics:[Topic]!
	getTopic(id:Int):Topic
}

type Mutation {
	createTopic(title: String!, body: String): Topic 
}
```

`type Query` 데이터 요청 

```jsx
endpoint = 'graphql';
queryCode = `
{
    title
}
`;
options = {
    method: "POST",
    headers:{'Content-Type':'application/json'},
    body: JSON.stringify({
        query: queryCode
    })
}
fetch(endpoint, options);
```

```jsx
endpoint = 'graphql';
queryCode = `
{
    title
    topics{
		id title 
  }
  getTopic(id:1) {
		id title 
	}
}
`;
options = {
    method: "POST",
    headers:{'Content-Type':'application/json'},
    body: JSON.stringify({
        query: queryCode
    })
}
fetch(endpoint, options);
```

```jsx
endpoint = 'graphql';
queryCode = `
query($topicId:Int!){
    title
    topics{
		id title 
  }
  getTopic(id:$topicId) {
		id title 
	}
}
`;
variables = {"topicId":1}
options = {
    method: "POST",
    headers:{'Content-Type':'application/json'},
    body: JSON.stringify({
        query: queryCode,
        variables:variables
    })
}
fetch(endpoint, options);
```

`mutation` 데이터 수정 삭제
