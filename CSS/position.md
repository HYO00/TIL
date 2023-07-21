### Position 

- Static 
  기본값

  left, right, top, bottom 비활성화 됨 

- Relative
  원래 자기가 있던 위치를 기준으로 위치를 정한다. 

  부모태그의 위치를 기준으로 해서 자신의 위치가 결정된다.

  부모에 대해서 상대적이다.

- Absolute
  부모 요소를 기준으로 위치를 정한다.

  자기의 크기를 가지게 된다. 컨텐츠 크기

  공중부양한다..

  부모의 값이 position이 static이 아닐 때만 부모를 기준으로 top, right, bottom, left 값을 결정한다.

- Fixed
  뷰포트를 기준으로 위치를 정한다.
  
  자기의 크기를 가지게 된다. 컨텐츠 크기

  scroll 해도 그자리에 있ㄴ는다. 
  
  -  헤더 고정
  -  페이지 상단 하단 이동 버튼
  -  팝업 배너
 
Static이 아닐 때 영향을 주는 속성 - zIndex도 알아보자
