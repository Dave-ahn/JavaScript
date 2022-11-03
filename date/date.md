# JavaScript 현재시간과 날짜



## 오늘은 자기소개 웹 페이지에 자바스크립트 기능을 추가하는 작업을 하였다.
<br>

## 무슨 기능을 넣을까 고민이 많이 되었다.

<br>

왜냐하면 자기소개 웹에 많은 기능을 넣게되면
오히려 방문자에게 반감을 일으키지 않을까 생각이 들었다.

## 그래서 날짜와 현재시간 기능을 추가하려고한다.
<u><i>(깔끔하고 심플하니까.)</i></u>

<br>

***
<br>

### 우선 index.html 에 div 태그로 날짜와 시간을 넣어줄 공간을 만들어 주자

```html
    <div id="date" class="date">date</div>
    <div id="time" class="time">time</div>
```

### 그다음 setClock이라는 함수를 선언하고 today라는 변수에 Date() 생성자를 할당해주고 이어서 year/month/day/hour/min/sec 순으로 변수를 선언해준다.

```javascript

function setClock(){
const today = new Date();
const year = today.getFullYear();
const month = today.getMonth()+1; 

/*
컴퓨터는 0부터 시작하기때문에 1월 부터 시작한 해당 월을 카운팅 하려면 +1해줘야한다.(그렇지 않으면 1월은 0월로 표시될 수 있다.)
*/


const day = today.getDate();
const hour = modifyNumber(today.getHours());
const min = modifyNumber(today.getMinutes());
const sec = modifyNumber(today.getSeconds());
```

### 그다음 변수중 시간 부분(hour/min/sec)은 modifyNumber()로 묶어주었다. 이유는 밑에서 설명 하겠다.

```javascript
const formatDate = year+"."+(("00"+month.toString()).slice(-2))+"."+(("00"+day.toString()).slice(-2));
```

### 위의 변수 formatDate에 (("00"+month.toString()).slice(-2)) 와 (("00"+day.toString()).slice(-2))를 설정해주었다.

<br>

### 이렇게 설정해 놓으면 "10미만의 해당 월(month)" 과 "10미만의 해당 일(day)" 앞에 문자열 "00"이 붙게되고,

<br>

### 뒤에 slice(-2)를 통하여 뒤 두 글자만 가져오게 된다.

<br>

### 이는 9월 일경우 009로 표기되고 slice(-2)를 통하여 "09" 로 표시된다.
### 이렇게 표시 할 경우 <h2><u>2022."9".30</u></h2> 로 표시되는것보다 <h2><u>2022."09".30</u></h2>이 훨씬 깔끔하고 보기 좋다고 생각한다.

```javascript
document.getElementById("date").innerHTML = formatDate
document.getElementById("time").innerHTML = hour + ":" + min + ":" + sec;
}
```
```javascript
function modifyNumber(time){
    if(parseInt(time)<10){
        return "0" + time;
    }
    else return time;
}
```
### 그 다음은 modifyNumber함수를 선언하고 input자리에 time을 넣어주므로써 앞서 선언한 변수 hour/min/sec 들이 time에 귀속하게 된다.
<br>

### 이 함수는 if문으로 parseInt()함수를 사용하여 time을 숫자로 변환했을때 값이 10보다 작으면 문자열 0과 숫자를 같이 출력되어 두자리 숫자인것처럼 보여지게 만드는 함수이다.

```javascript
window.onload = function(){
    setClock();
    setInterval(setClock,1000); // 1초 간격으로 secClock 함수 실행.
}
```
### 마지막으로 매 1초마다 함수 setClock 이 작동될 수 있도록 setInterval함수안에 (setClock,1000ms)로 입력해주었다.
