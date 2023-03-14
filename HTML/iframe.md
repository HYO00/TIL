https://developer.mozilla.org/ko/docs/Web/HTML/Element/iframe

### iframe?

HTML Inline Frame 요소이며 inline frame의 약자

The <iframe> HTML element represents a nested browsing context, embedding another HTML page into the current one.

다른 HTML 페이지를 현재 페이지에 포함시키는 중첩된 브라우저로 iframe 요소를 이용하면 해당 웹 페이지 안에 또 다른 독립적인 웹페이지를 포함하여 렌더링 할 수 있다.

쉽게 다른 도메인에서 제공하는 콘텐츠를 삽입해 사용할 수 있지만 CORS에러가 발생할 수 있다. 

CORS 에러가 발생하지 않으려면, 현재 도메인과 iframe으로 불러올 도메인 사이에서 요청과 응답에 필요한 CORS 설정이 모두 잘 이루어져있어야 한다. 

```jsx
// 문법
<iframe src="삽입할페이지주소" width="너비" height="높이"></iframe>

// 예시
<iframe src="./intro.html" width="300" height="300"></iframe>
```

속성

- src : 삽입 할 홈페이지 
- url- name : 프레임 이름
- width : 프레임 가로 너비
- height : 프레임 세로 길
- frameborder : 프레임 테두리 선 (0으로 설정하면 프레임의 테두리선 x, 1로 설정하면 프레임의 테두리선 o)
- scrolling : 스크롤바의 표시 여부를 나타냅니다. (yes로 설정하면 스크롤 바 무조건 표시, auto는 자동 표시)


### **Browsing context**

**document 객체들이 사용자에게 표현되는 환경**

it usually is a *tab*, but can be a *window* or even only parts of a page, like a *frame* or an *iframe*
Each browsing context has a specific origin, the origin of the active document and a history that memorize all the displayed documents, in order.

[https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context)
