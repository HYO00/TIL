## Viewport meta tag

브라우저의 vieport는 웹 콘텐츠를 볼 수 있는 영역이다. 

기본 해상도 1920 * 1080 화면의 경우 가로 1920, 세로 1082 픽셀이 배치되어 있는 것이다. 

뷰포트를 지정
- meta 태그를 할용해 실제 보여지는 영역의 너비, 높이, 확대 또는 축소에 대한 값을 지정한다.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

속성 

- width 
  viewport 너비 지정

- height
  viewport 높이 지정

- initial-scale
  초기 확대/축소 값을 지정
  - initial-scale=1.0 (기본값)
  - 0.1~10 사이의 값
  - 값이 클수록 확대된 화면 로딩

- minimum-scale
  축소율의 최소값을 지정
  - minimum-scale=0.1 (기본값)
  - 0.1~10 사이의 값


- maximum-scale
  확대율의 최대값을 지정
  - maximum-scale=10 (기본값)

- user-scalable
  사용자의 확대/축소 가능 여부를 지정
  - 0,1,yes, no로 설정


:::caution

Usage of user-scalable=no can cause accessibility issues to users with visual impairments such as low vision. WCAG requires a minimum of 2× scaling; however, the best practice is to enable a 5× zoom.

:::

- interactive-widget
  Specifies the effect that interactive UI widgets, such as a virtual keyboard, have on the page's viewports. 
  - Valid values: resizes-visual, resizes-content, or overlays-content. Default: resizes-visual.

### 브라우저 viewport 구하기 

- document.documentElement.clientWidth / clientHeight

문서의 viewport 크기

- window.innerWidth / innerHeight

브라우저 viewport 의 스크롤 포함 크기

- window.outerWidth / outerHeight

브라우저 창 크기

