# grahql + react query


### grahql
그래프 큐엘 혼자서는 아무것도 못한다. 

그래퓨 큐엘은 요청 전 어떻게 요청을 보낼건지 정의를 해두는 것이다. 

### react query

리액트 쿼리 혼자서도 아무것도 못한다. 

리액트 쿼리를 사용해서 상태관리를 할 수 있다

useQuery는 get api요청하기 위한 hook이다. 그래프큐엘과 함께 사용시 그래프큐엘 클라이언트를 사용해 요청을 보낸다. 

useQueries 

queryKey (unique key) 해당 쿼리의 고유 식별자 

queryFn : 쿼리에 사욯할 promise 기반의 비동기 api (요청 함수)
