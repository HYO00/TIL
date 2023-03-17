## CSS Flexbox

css 속성 중 flex 속성을 많이 쓰지만 사용 방법에 대해 제대로 알지 못했다. 

[https://d2.naver.com/helloworld/8540176](https://d2.naver.com/helloworld/8540176) 해당 글을 참고하여 flexbox를 이해해보자.


### Flexbox?

뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때 효율적으로 요소를 배치, 정렬, 분산할 수 있는 방법을 제공하는  css3의 새로운 레이아웃 방식이다. 

정렬, 방향, 순서, 크기 등을 유연하게 조절할 수 있다. 

flexbox는 복수의 자식 요소인 flex item과 그 상위 부모 요소인 flex container로 구성된다.

![Untitled](https://user-images.githubusercontent.com/79884004/225895541-215df2d8-a6d1-47d2-a8a0-c0f608a2bf8b.png)


정렬하려는 요소의 부모 요소에 `display:flex` 속성을 선언한다. 

`flex`속성이 적용된 요소는 flex container가 되고, flex container의 자식 요소는 flex item이 된다.

 flex item은 주축에 따라 정렬되고 주축의 방향은 flex container의 flex-direction속성으로 결정된다. 속성을 따로 지정하지 않으면  기본 값은 row이다. 

전체적인 정렬이나 흐름에 관련된 속성은 flex container에 정의하고, 자식 요소의 크기나 순서에 관련된 속성은 flex item에 정의한다.

![Untitled (1)](https://user-images.githubusercontent.com/79884004/225895569-6e67235b-6cd9-4601-a97f-3f4d5a742da9.png)


### flex 속성

- flex-grow 

    값이 0일 때 flex container의 크기가 커져도 flex item의  크기가 커지지 않고 원래 크기 유지

    크기가 커질 때 flex item 크기도 커지게 하려면 1 이상의 속성 값으로 설정한다.

- flex-shrink

    값이 0일 때 flex container의 크기가 작아 flex item의  크기가 작아지지 않고 원래 크기 유지

    크기가 커질 때 flex item 크기도 작아지게 하려면 1 이상의 속성 값으로 설정한다.

- flex-basis

    flex item의 기본 크기를 결정하는 속성이다. 기본값은 `auto`다.

    `width`속성에서 사용하는 모든 단위(px, %, em, rem 등)를 속성값에 사용할 수 있다.

    `flex-basis`속성의 값을 `0`으로 설정하면 flex item은 절대적 flex item(absolute flex item)이 되어 flex container를 기준으로 크기가 결정된다.

    | flex | flex-grow | flex-shrink | flex-basis |
    | --- | --- | --- | --- |
    | initial(기본값) | 0 | 1 | auto |
    | none | 0 | 0 | auto |
    | auto | 1 | 1 | auto |
    | 양의 정수 | 숫자 | 1 | 0 |

- 푸터 바닥에 고정하기 

    ```jsx
    .map_wrap {
      display: flex;
      flex-direction: column;
      height: 100vh;	
    }
    .footer {
        background-color: white;
        height: 100px;
        margin-top: auto;
    }
    ```

- flex-wrap 

    flex-wrap은  flex item이 flex contaienr를 벗어났을 때 줄을 바꾸는 속이다. 

    flex-wrap: wrap 속성은 flex item의 전체 크기가  flex container 보다 크면 줄을 바꿔 여러 줄로  flex item을 배치한다. 

    align-content 속성은 flex item 이 여러 줄로 나열되어 있을 때 주축을 기준으로 수직 정렬 방법을 설정하는 속성이다.
