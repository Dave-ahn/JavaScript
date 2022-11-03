# getMonth() 메소드의 실체 

자바 스크립트에서 날짜를 구하려면 Date 객체를 활용해야한다.

그 중 해당 달(月)을 구하려면 

getMonth() 메소드를 사용해야한다.

<br> 

***

<br> 

자바스크립트로 코드를 작성하면

```JavaScript
function setDate(){
const today = new Date();
const year = today.getFullYear();
const month = today.getMonth()+1;
const day = today.getDate();

document.getElementById("date").innerHTML = year + "." + month + "." + day //2022.10.5
}
```

위 처럼 간단하게 표기했을때는 위처럼 작성하여 표기할 수있다.

그런데 의문이었던것은 왜 <u>"getMonth()"</u> 메소드만 뒤에 +1이 붙는것일까?

처음 날짜 표기 기능을 찾아보며 이해했던바로는 <i>"컴퓨터는 0부터 시작되니까 1월은 0월이 되는건가?"</i>  였지만 이건 틀린 생각인것 같다.

왜냐하면 위와같은 논리라면 일(日)을 나타내는 getDate()메소드 역시 "0일" 부터 시작해야되는것 아닌가?

<br> 

>## 이에 대한 간단한 답 :

 getMonth()메소드는 Zero-base 로 설정되어있기 때문에 +1을 해줘야 정상적인 해당 달이 출력된다.

<br>

***

<br>

> ## 그럼 대체 왜 Zero-base로 설정되어있는거지?

<br> 

만약 getFullYear()이나 getDate()역시 Zero base (0 base)로 설정되어있었다면 납득했을 것이다.
하지만 뭔가 이상하지 않은가?

왜 다른것도 아니고 getMonth()메소드만 Zero base (0 base)로 되어있는거지?

<br> 

***

<br> 

>## JavaScript와 JAVA

<br>

JavaScript의 날짜 표기는 Java JDK1.0(1995) 버전을 카피했다고 한다.

*JDK=Java Development Kit(자바 개발 키트)

<br> 


Java에서 날짜와 시간을 다루려면 java.util.Date 클래스와 java.util.Calendar 클래스를 사용해야 하는데 JDK 8(2014) 이전에 버전은 여러 가지 문제점이 있었다.

<br> 

특히 본 문에서 다루고 있는 "Zero-base month" 문제가 JDK 8버전 이전까지 계속 사용되어온 것으로 보인다.

<br> 

이에 불만을 품은 유저들은 Joda-Time와 같은 오픈소스 라이브러리를 만들어 사용했으며 결국 JDK 8 이후에 날짜와 시간 API가 개선되었다.

<br> 

따라서 JavaScript의 날짜와 시간 표기 방식은 JDK 8 이전의 방식을 채택하고 있으므로 발생하는 작은 문제라고 한다.

<br> 

이에 JavaScript 창조자인 브렌던 아이크(Brendan Eich)는 트위터에

<br> 

"I had ten days to demo. No time to invent our own date API or even fix Java's" 라고 답변하였다.

<br> 

10일 만에 JavaScript 데모를 만들어낼 정도의 능력자이니 이정도 작은 실수는 살짝 눈 감아주는것이 좋을듯 싶다.

>😉

<br> 

***

<br>


>## 결론


<br>

 JavaScript가 채택한 날짜와 시간 표기법은 JDK 8 이전 버전에서 설정 되어있는 "Zero-base month" 기능의 영향으로 getMonth() 뒤에 +1을 추가로 입력해줘야하는 것이다.

<br>

***

<br>

-후기

<h5>"대체 왜?" 라는 질문은 언제나 가치있는 답을 해준다.

"그냥"이라는 말을 좋아하지 않기에 불편했고,
불편했기에 답을 찾으려 노력하고있다.

오늘은 조금 편하게 잠들수 있을듯.

<br> 

2022.10.05 17:59

Dave Ahn <h5>