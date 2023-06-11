### svg import 차이
```import  Like  from "../../../assets/like.svg";```

- Like 변수는 해당 SVG 파일의 default export를 참조
- default export는 모듈에서 기본적으로 내보내지는 단일 값 또는 객체

vs 

```import { Like } from "../../../assets/like.svg";```

- Like 변수를 like.svg 파일에서 가져온다.
- like.svg 파일에서 명시적으로 내보낸 named export인 Like를 가져오기
- named export는 모듈에서 여러 개의 값을 내보낼 때 사용
