# EventListener

오늘은 addEventListener(이벤트 리스너)라는 메서드에 대하여 알아보자.

이벤트 메서드는 자바 스크립트에서 굉장히 유용하게 사용된다.

## 콜백 함수

<br>

자바 스크립트는 위에서 아래로 읽히는데 이 addEventListener 메서드를 사용하게 되면 메서드 내에서 특정 동작이 발생하였을 때 addEventListener가 가지고 있는 함수가 실행된다.

이를 "콜백 함수"라고 부른다.


> ### 콜백 함수 : 1. 다른 함수의 인자로써 이용되는 함수. 2. 어떤 이벤트에 의해 호출되는 함수.

<br>

그렇다면 이벤트 리스너는 무엇을 의미하는가?

말 그대로 Event가 발생하기 전까지 Listen 하고 있는다는 뜻으로 볼 수 있다.

특정 "이벤트 = 행동" 발생하는 것을 "리슨 = 듣고 있는다."

즉, 행동을 기다리고 있다는 뜻이다.

***

## 그럼 왜 이벤트 리스너를 사용하는가?

<br>

자바스크립트는 동적인 프로그래밍 언어이다.

가령 우리가 HTML 와 CSS로 만든 웹 페이지를 만들었다면,

그 웹 페이지에 특정 행동이 발생하는 장치를 만들고 그 특정 행동에 발생하였을 때 대한 다른 기능이 발생하는 것을 구현하려면 이벤트 리스너를 사용해 주어야한다.

***

## 이벤트 종류

eventlistener 메서드가 가지고 있는 다양한 이벤트 동작이 있다.

대표적으로 click, keyup, mouseover 등등이 있다.

click 이벤트 경우 onclick과 비슷한 기능이다.

아래는 click 이벤트를 활용한 예제이다.

```html
<!-- 스타일 -->
<style>
/* 주축 가운데 정렬 */
#btnBox {
    display: flex;
    justify-content: center;
}

/* 가로 X 세로 100px 박스 */
#clickBtn {
    width: 100px;
    height: 100px;
}
</style>
</head>
<body>

<!-- 버튼 -->
<div id="btnBox">
<input type="button" id="clickBtn" value="click">
</div>

<!-- 스크립트 -->
<script>
let buttonClick = document.getElementById("clickBtn");

buttonClick.addEventListener("click",function(){
    alert("Hello!");
})
</script>
```

우선 보기 편하게 가로 X 세로 100px 크기의 버튼을 하나 만들어 주었다.

그다음 **"clickBtn"** 이라는 아이디를 가진 요소(=button)를 HTML 문서에서 가지고 와서 **"buttonClick"** 이라는 함수를 선언해 주었다.

이 변수 buttonClick에 **"addEventListener"** 라는 메서드를 적용시켜 **"click"** 이라는 특정 행동이 발생하였을 때 **function(){alert("Hello!");}** 라는 함수가 실행 되도록 장치를 만들어 놓은 것이다.

(gif 첨부)

위에 보이는 gif 파일처럼 누를 때마다 "Hello!" 라는 알림창이 뜨는 것을 확인할 수 있다.

사용자의 어떠한 특정한 이벤트(행동)가 발생할 때 마다 함수가 호출되는 것이다.

***

<h5>

-후기

이벤트 리스너는 정말 정말 정말 중요한 메서드이다.
모든 이벤트의 종류를 외울 필요는 없지만 필요한 순간에 바로바로 사용할 수 있도록 사용법은 꼭 익혀야 한다.

2022.10.27(목) 10:04 Dave Ahn
</h5>