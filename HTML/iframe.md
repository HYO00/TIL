iframe?

### iframe?

HTML Inline Frame 요소이며 inline frame의 약자

다른 HTML 페이지를 현재 페이지에 포함시키는 중첩된 브라우저로iframe 요소를 이용하면 해당 웹 페이지 안에 어떠한 제한 없이 다른 페이지를 불러와서 삽입 할 수 있다.

```jsx
// 문법
<iframe src="삽입할페이지주소" width="너비" height="높이"></iframe>

// 예시
<iframe src="./intro.html" width="300" height="300"></iframe>
```

속성

src : 삽입 할 홈페이지 

url- name : 프레임 이름

width : 프레임 가로 너비

eight : 프레임 세로 길

frameborder : 프레임 테두리 선 (0으로 설정하면 프레임의 테두리선 x, 1로 설정하면 프레임의 테두리선 o)

scrolling : 스크롤바의 표시 여부를 나타냅니다. (yes로 설정하면 스크롤 바 무조건 표시, auto는 자동 표시)
