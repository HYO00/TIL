## Analyze runtime performance

런타임 성능은 페이자 로딩될 때 성능과 달리 페이지가 실행 중일때 성능을 말한다. 

Chrome DevTools 성능 패널을 사용하여 런타임 성능을 분석하는 방법을 알아보자 

1. 크롬 시크릿창으로
2. https://googlechrome.github.io/devtools-samples/jank/ 들어가기
3. 개발자 도구 열기

### Simulate a mobile CPU

웹 페이지를 프로파일링할 때, CPU Throttling을 사용하여 페이지가 모바일 장치에서 어떻게 실행되는지 시뮬레이션하는지 보자

1. 개발자 도구 Performance tab. 클릭
2. Screenshots checkbox 확인
3. capture Settings  클릭. 

- 웹 페이지 프로파일링?
  
  웹 애플리케이션 또는 웹 사이트의 성능, 메모리 사용, 실행 시간 등과 같은 다양한 측면을 분석하고 측정하는 과정이다.

  이를 통해 웹 페이지의 성능 병목 현상을 식별하고 최적화할 수 있다.

  - 자바스크립트 코드에서 실행 시간이 오래 걸리는 부분 식별
  - 느린 네트워크 요청 및 리소스 로딩 시간 확인
  - 메모리 누수 및 비효율적인 메모리 사용 식별
  - 렌더링 지연 및 성능 저하 요인 확인

### Set up the demo

1. 파란 사각형이 느려질 때 까지 추가 버튼 클릭 하기
2. Click Optimize
  파란 사각형이 빨리 움직이기 시작
3. Click Un-Optimize 다시 느리고 버벅거림

### Record runtime performance
1. 개발자 도구 성능탭 click Redcord
2. 몇 초 기다리기
3. 주이지 클릭하고 패널에 결과보기
   
![화면 캡처 2023-07-05 150950](https://github.com/HYO00/TIL/assets/79884004/ce154499-787b-438a-9657-e815dc4a9c37)

### Analyze the results

페이지 성능 기록으로 해당 페이지 성능이 얼마나 나쁜지 측정하고 원인을 찾을 수 있다. 

### Analyze frames per second 
어떤 애니메이션든 성능을 측정할때 주요한건 초당 플레임 (FPS)이다. 
사용자는 애니메이션이 60FPS로 실행되어야 만족한다. 

1. Look at the FPS chart. 
  아래 사진처럼 FPS가 빨간 막대면 사용자 경험은 안좋다.
  일반 적으로 초록 막대면 FPS가 좋은걸 의미한다. 
![red fps](https://github.com/HYO00/TIL/assets/79884004/522b359e-1a96-4327-b79b-82d85443e735)

2. CPu 탭은 요약 summary탭에서 볼 수 있다.

   CPU chart가 색으로 가득 찼다면 cpu가 최대로 사용되었다는 걸 의미한다.  ->  it's a cue to find ways to do less work.
3. 해당 시점의 페이지 스크린샷을 마우스를 움직여 확인해보기
4. 프레임 섹션은 특정 프레임에 대한 FPS를 보여준다.

### Find the bottleneck

1.  summary tab 확인 - 무슨 시간이 오래걸리는지
2.  main 영역 
  - x축은 시간 경과에 따른 기록
  - 각 막대는 이벤트
  - 넓은 막대는 오래걸림을 의미
  - y축은 call stack 의미 

...작성중

https://developer.chrome.com/docs/devtools/performance/

